#### 获取指定地址比特币余额
````
omnicore-cli -rpcuser=sung -rpcport=8899 -rpcpassword=Aa123456 getreceivedbyaddress "mpCLCyRyyk7xyTcMPLSLa4vqA73YVA3ro9"
0.06476174
````

#### 获取代币余额：
````
omnicore-cli -rpcuser=sung -rpcport=8899 -rpcpassword=Aa123456 "omni_getbalance" "mxF4ZXM9HobpiNEecEDFvzzZLeEA5iQwkN" 2
{
  "balance": "10.00000000",
  "reserved": "0.00000000",
  "frozen": "0.00000000"
}
````

#### 获取交易信息：
````
omnicore-cli -rpcuser=sung -rpcport=8899 -rpcpassword=Aa123456 gettransaction 7d725ab3907be3315da676102d0190ab6f656c1cb036d185a274f2b88293238a
{
  "amount": -0.10000000, //交易金额，正数表示该交易增加钱包余额，负数表示该交易减少钱包余额
  "fee": -0.00000450, //交易手续费，仅针对转出交易
  "confirmations": 12, //交易确认数，0表示未确认，-1表示存在冲突
  "blockhash": "000000000000043c84da71c5cd9a475334cf8c233b157462812f9ff3dd1a6c4e", //交易所在区块的哈希
  "blockindex": 23, //交易所在区块的编号
  "blocktime": 1560137538, //交易所在区块的unix时间
  "txid": "7d725ab3907be3315da676102d0190ab6f656c1cb036d185a274f2b88293238a", //交易ID
  "walletconflicts": [ //冲突交易数组，成员为冲突交易的ID
  ],
  "time": 1560137415, 
  "timereceived": 1560137415, //节点收到交易的unix时间
  "bip125-replaceable": "no", //是否可替换交易
  "details": [ 
    {
      "account": "", //交易影响的账户名称
      "address": "moneyqMan7uh8FqdCA2BV5yZ8qVrc9ikLP", //对端地址
      "category": "send", //send：发送交易 receive：接收交易 
      "amount": -0.10000000,
      "vout": 1,
      "fee": -0.00000450,
      "abandoned": false
    }
  ],
  "hex": "01000000017498c81a2cdf16d524797f94eed5d1a167cd8713135bc6569fa1ab51b3f5dd80010000006a47304402202e6e9b7c5df1eb9b17b6d58dd2aecf209d59d3a162d25a1048e3b54f3f50f1b402202d6b3c6623c17029b5adb94b5ed338aec3046f3f5acfa8db244aa80941aa2a69012103c2df4fcf357946b17d0e0981d7b9e718c8b749e2019fa8a67a0aee595bfbaabafeffffff02daf95000000000001976a914e4bc9c10c07d7607f3b6ecaed3e4489b4dc437e688ac80969800000000001976a9145ab93563a289b74c355a9b9258b86f12bb84affb88ac42851700"
}
````

#### 返回钱包内账户及对应余额
````
omnicore-cli -rpcuser=sung -rpcport=8899 -rpcpassword=Aa123456 -testnet listaccounts
{
  "": -0.10000450,
  "1": 0.00000000,
  "10": 0.00000000,
  "myTest": 0.00000000,
  "myTest1": 0.00000000,
  "myTest2": 0.00000000,
  "mytest": 0.20691011
}
````

#### 调用返回每个钱包地址的所有代币余额信息
````
omnicore-cli -rpcuser=sung -rpcport=8899 -rpcpassword=Aa123456 -testnet omni_getwalletaddressbalances
[
  {
    "address": "mx5uTqen3Ub3VnorpyQYKCvr9SJQVxfZEM",
    "balances": [
      {
        "propertyid": 2,
        "name": "Test Omni tokens",
        "balance": "0.10000000",
        "reserved": "0.00000000",
        "frozen": "0.00000000"
      }
    ]
  },
  {
    "address": "mxF4ZXM9HobpiNEecEDFvzzZLeEA5iQwkN",
    "balances": [
      {
        "propertyid": 1,
        "name": "Omni tokens",
        "balance": "10.00000000",
        "reserved": "0.00000000",
        "frozen": "0.00000000"
      },
      {
        "propertyid": 2,
        "name": "Test Omni tokens",
        "balance": "9.90000000",
        "reserved": "0.00000000",
        "frozen": "0.00000000"
      }
    ]
  }
]
````

#### 调用返回指定地址的所有代币余额
````
omnicore-cli -rpcuser=sung -rpcport=8899 -rpcpassword=Aa123456 -testnet omni_getallbalancesforaddress mxF4ZXM9HobpiNEecEDFvzzZLeEA5iQwkN
[
  {
    "propertyid": 1,
    "name": "Omni tokens",
    "balance": "10.00000000",
    "reserved": "0.00000000",
    "frozen": "0.00000000"
  },
  {
    "propertyid": 2,
    "name": "Test Omni tokens",
    "balance": "10.00000000",
    "reserved": "0.00000000",
    "frozen": "0.00000000"
  }
]
````

#### 查询账户下的地址
````
omnicore-cli -rpcuser=sung -rpcport=8899 -rpcpassword=Aa123456 -testnet getaddressesbyaccount "mytest"
[
  "mxF4ZXM9HobpiNEecEDFvzzZLeEA5iQwkN"
]
````