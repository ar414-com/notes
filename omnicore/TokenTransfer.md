>#### USDT 
> USDT的转账实际上是代号为31的OmniCore令牌转账。Omnicore提供了多套api实现令牌转账功能，v0.3.1版本之前，可以使用omni_send和omni_sendall。这种方式必须保证发送地址上不仅需要有令牌余额，还需要有一定数量的比特币用于支付手续费。从v0.3.1版本开始，Omnicore提供了两个新的api omni_funded_send和omni_funded_sendall，这种方式的好处在于可以指定手续费的支付方，所有的令牌交易都可以使用统一的地址进行支付比特币手续费，而不需要发送者自身拥有比特币。但这里并未设定手续费的具体数量，系统将根据在配置文件中的关于手续费的配置文件进行动态设定。
> 
>方法 omni_funded_send
> 参数：
> * fromaddress (string,必选) 令牌发送者
> * toaddress (string,必选) 令牌接收者
> * propertyid (number,必选) 令牌id
> * amount (string,必选) 发送金额
> * feeaddress (string,可选)用于支付手续费的地址，如果设置此地址，那么此地址上必须拥有比特币
>
> 返回：事务HEX
````
$ ./omnicore-cli omni_funded_send mjH1iB7wt5TC4f8qjvZqtmBXd1aCPSPinC mqrA5Ai8XdKe1ob1L2HwyYr3TXUf9nUeBf 1 5 mpaumxor659PhoJhXp1VCVHVwbFCZSRmuf
a25260a79243a48df21ca2d9fba2209818ea1339026d91b6476d531929c52dad
````
