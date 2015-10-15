# lumen-api-demo

一个用lumen写api的例子

- 使用[dingo/api](https://github.com/dingo/api)
- 使用[jwt(json-web-token)](https://github.com/tymondesigns/jwt-auth)

##使用dingo API
教程 [http://vea.re/blog/150905-api-with-dingo-and-lumen-part-1](http://vea.re/blog/150905-api-with-dingo-and-lumen-part-1)

lumen 关闭了好多功能，所以要先修改一下才能使用

大概步骤是:

1. 修改bootstrap/app.php，打开 `Dotenv::load(__DIR__.'/../')`,这样就可以加载.env文件了
2. 打开 `$app->withEloquent()`，因为要使用orm
3. 注册dingo的服务 `$app->register(Dingo\Api\Provider\LumenServiceProvider::class)`,添加到80行左右那个位置。
4. 然后就可以按照dingo的文档使用了

		$api = app('Dingo\Api\Routing\Router');

		$api->version('v1', function($api){
		    $api->get('collections/{collection}', function(){
		        return 'test';
		    });
		});


## 使用jwt
教程 [http://laravelista.com/json-web-token-authentication-for-lumen/
](http://laravelista.com/json-web-token-authentication-for-lumen/
)

这个库`tymondesigns/jwt-auth`图片的大标题写着 for laravel & lumen
但是！！还没有支持lumen，所以要按照上面的教程一步一步做很多工作。

[https://github.com/generationtux/jwt-artisan](https://github.com/generationtux/jwt-artisan) 这个库支持了lumen, 已尝试，可以用。不过看关注和代码，所以还是研究一下`tymondesigns/jwt-auth`这个吧

还在调试......
