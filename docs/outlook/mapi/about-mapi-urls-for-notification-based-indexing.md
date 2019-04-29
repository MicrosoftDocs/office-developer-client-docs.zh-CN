---
title: 关于基于通知的索引的 MAPI url
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: 9cb35f0a-267e-2d85-1701-02d52578a0b8
description: '上次修改时间: 2011 年11月8日'
ms.openlocfilehash: 5a3e45809f36b71968560a4b239e268addf00474
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33422479"
---
# <a name="about-mapi-urls-for-notification-based-indexing"></a>关于基于通知的索引的 MAPI url

**适用于**：Outlook 2013 | Outlook 2016 
  
当存储提供程序通知索引器对象已准备好编制索引时, 它将生成一个 mapi URL, 该 URL 将对象唯一标识为 mapi 协议处理程序。 MAPI url 采用 Unicode 编码, 格式如下: 
  
`Mapi://SID/StoreDisplayName ($HashNumber)/StoreType/FolderNameA/…/FolderNameN/[EntryIDEncoded[/at=AttachIDEncoded:FileName]]`

下表介绍了典型 URL 的各个部分。

|Part | 说明|
|:----|:-----------|  
|*SID* |当前用户的安全标识符。| 
|*StoreDisplayName* |一个字符串, 它指定该存储区上的用户的显示名称。|
|*HashNumber* |十六进制表示法中的一个**DWORD**值, 基于存储项 ID 或存储区映射签名计算。 此值存储在注册表中, 稍后将用于标识 MAPI 协议处理程序中的存储区。<br/><br/>此数字必须以最小化与其他存储区的冲突的方式计算。 有关 Microsoft Outlook 用于计算哈希值的算法, 请参阅[算法计算存储哈希数](algorithm-to-calculate-the-store-hash-number.md)。|
|*StoreType* |一个数字, 用于标识包含要编制索引的对象的存储区的类型。 可能值包括：<br/>-0-默认存储区。<br/><br/>-1-代理存储, 用于委派本地缓存的项目。<br/><br/>-2-公用文件夹, 用于公用文件夹收藏夹。<br/><br/>**注意**: 如果正在对存储进行爬网而不是推送, 则使用的值是字符*X*。| 
|*FolderNameA/.../FolderNameN* |从 IPM_SUBTREE 的根目录到文件夹或邮件的路径。 例如, 在 "**收件箱**" 下的 "**家庭**" 文件夹中的邮件包含此参数的**收件箱/家庭**。 |
|*EntryIDEncoded* |编码为 Unicode 字符串的项目的 MAPI 条目 ID。 有关如何对特定特殊字符进行编码的信息, 请参阅以下部分 "特殊字符"。 有关用于对条目 id 进行编码的算法的详细信息, 请参阅[算法对条目 id 和附件 id 进行编码](algorithm-to-encode-entry-ids-and-attachment-ids.md)。<br/><br/>**注意**: 作为文本查看时, 此编码的条目 ID 将显示为符合算法的随机朝鲜语字符或方框, 具体取决于可用的字体。  |
|*AttachIDEncoded* |编码为 Unicode 字符串的附件 ID。 有关如何对特定特殊字符进行编码的信息, 请参阅以下部分 "特殊字符"。 有关用于对条目 id 进行编码的算法的详细信息, 请参阅[算法对条目 id 和附件 id 进行编码](algorithm-to-encode-entry-ids-and-attachment-ids.md)。<br/><br/>**注意**: 作为文本查看时, 此编码的条目 ID 将显示为符合算法的随机朝鲜语字符或方框, 具体取决于可用的字体。 |
|*FileName* |附件文件在邮件中显示时的名称。|
    
## <a name="examples-of-mapi-urls"></a>MAPI url 的示例

以下是 MAPI url 的一些示例。
  
- 文件夹的 MAPI URL: 
    
  `mapi://S-1-5-21-2127521184-1604012920-1887927527-71418/Mailbox - Some User ($be19928f)/2/Office`
    
- 邮件的 MAPI URL: 
    
  `mapi://S-1-5-21-2127521184-1604012920-1887927527-71418/Mailbox - Some User ($484efb89)/0/Calendar/곯가가가걍걝걌곌겷걢곒갑겛개가검걟곔걙곾걤곂갠가`
    
- 附件的 MAPI URL: 
    
  `mapi://S-1-5-21-2127521184-1604012920-1887927527-71418/Mailbox - Some User ($484efb89)/0/Inbox/곯가가가걍걝걌곌겷걢곒갑겛개가검걟곔걙곾간곷갦가/at=겅걋각가:somefile.txt`
    
## <a name="special-characters"></a>特殊字符

如果某些字符出现在邮件或附件中, 则对其进行编码。 下面显示了在 MAPI URL 中编码的字符:
  
- % >% 25
    
- />% 2f 
    
- \ >% 5c 
    
- \*>% 2a 
    
- ? >% 3F 
    
## <a name="blob-associated-with-each-mapi-url"></a>与每个 MAPI URL 相关联的 Blob

为要编制索引的对象推送 MAPI URL 时, 存储提供程序还会创建一个二进制大型对象 (BLOB), 其中包含 MAPI 协议处理程序的特定信息。 存储提供程序将此 BLOB 与每个 mapi url 相关联, 并在将 MAPI url 推送到索引器时发送该 url。 BLOB 的格式如下所示: 
  
```cpp
DWORD  dwVersion
DWORD  dwFlags
ULONG  cbProfileName
WCHAR  wszProfileName
ULONG  cbProviderItemID
WCHAR  wszProviderItemID
```

存储提供程序必须按显示的顺序将这些值写入 BLOB。 下表介绍了 BLOB 的每个字段。

|Part | 说明|
|:----|:-----------|  
|*dwVersion* |这是要发送的数据的版本。 当前此值为1。|
|*dwFlags* |保留供以后使用。 当前此值应为0。|
|*cbProfileName* |配置文件名称的大小 (以字节为单位)。 此信息对 MAPI 协议处理程序很有用, 以知道在对项目编制索引时要使用哪个配置文件。|
|*wszProfileName* |以 Null 结尾的 Unicode 字符串, 其中包含配置文件名称。|
|*cbProviderItemID* |提供程序项目 ID 的大小 (以字节为单位)。 存储提供程序应仅发送文件夹的提供程序项目 ID, 以防止打开其他文件夹获取此信息。|
|*wszProviderItemID* |以 Null 结尾的 Unicode 字符串, 其中包含唯一标识存储中的项目的提供程序项目 ID。|
    
## <a name="see-also"></a>另请参阅

- [关于基于通知的存储索引](about-notification-based-store-indexing.md)
- [MAPI 常量](mapi-constants.md)

