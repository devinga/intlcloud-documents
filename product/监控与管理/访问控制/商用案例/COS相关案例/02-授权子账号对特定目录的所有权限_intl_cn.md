### 授权子账号对特定目录的所有权限

企业帐号CompanyExample（ownerUin为12345678,appId为1250000000）下有一个子账号 Developer，该子账号需要拥有对企业帐号CompanyExample的 COS 服务的上海地域名为 Bucket1 的存储桶的 dir1 目录的完全访问权限。

方案A：

step1：通过策略语法方式创建以下策略
```
{
    "version": "2.0",
    "statement":[
     {
         "effect": "allow",
         "action": "cos:*",
         "resource": ["qcs::cos:ap-shanghai:uid/1250000000:Bucket1-1250000000/dir1/*",
                    "qcs::cos:ap-shanghai:uid/1250000000:Bucket1-1250000000/dir1"]
     }
   ]
}
```
step2：将该策略授权给子账号。授权方式请参考[授权管理](https://intl.cloud.tencent.com/document/product/598/10602)。

方案B：

通过 COS 控制台进行 Policy 和 ACL 设置。具体请参考 COS 文档。
