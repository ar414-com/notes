#### 秒杀队列
````
//先将商品库存存入队列
<?php  
$store=1000;  //商品库存
$redis=new Redis();  
$result=$redis->connect('127.0.0.1',6379);  
$res=$redis->llen('goods_store');   

for($i=0; $i<$store; $i++){  
    $redis->lpush('goods_store',1);  
}  
echo $redis->llen('goods_store');  

//客户执行下单操作
$redis=new Redis();  
$result=$redis->connect('127.0.0.1',6379);
$count = $redis->lpop('goods_store');
if(!$count){
    echo '抢购失败！';
    return;
}    
````

#### 模糊删除KEY
````
redis-cli keys "user:token:vars:*"  |  xargs redis-cli del
````
