# XBX-Token

合约: contracts/xbx.sol  
合约测试脚本: test/xbx.test.js

---

## 安装 install
```bash
npm install -g npx  
npm install
```

---

## 编译 compile
1. truffle编译  
```bash
npx truffle compile
```

或者 Or

2. remix上在线编译  
如果在remix上在线编译，需要将xbx.sol合约开头的import进行替换，
具体见xbx.sol合约开头注释。solc选择0.8.4版本。

---

## 测试 test
```bash
npx truffle test
```

---

## 功能点设计 functionality
1. 符合ERC20合约接口规范  
2. 代币增发设置上限cap, cap可调整  
3. 关键方法采用基于role的访问控制， role可以授予给地址，也可以吊销  
4. 有两种类型的role，admin role和minter role：  
admin role权限：  
可以停止(pause/unpause)合约，停止后，合约transfer与mint均会失败  
可以授予，吊销其他账户的role  
minter role权限：  
minter可以增发token，admin role账户可以授权minter role给任意一个合约账户或者EOA账户。  
minter可以更改增发上限cap  