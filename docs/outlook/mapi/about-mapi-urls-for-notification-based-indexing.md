---
title: 关于用于索引Notification-Based MAPI URL
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: 9cb35f0a-267e-2d85-1701-02d52578a0b8
description: 上次修改时间：2011 年 11 月 8 日
ms.openlocfilehash: 5a3e45809f36b71968560a4b239e268addf00474
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33422479"
---
# <a name="about-mapi-urls-for-notification-based-indexing"></a>关于用于索引Notification-Based MAPI URL

**适用于**：Outlook 2013 | Outlook 2016 
  
当存储提供程序通知索引器某个对象已准备好编制索引时，它将生成一个 MAPI URL，用于唯一标识 MAPI 协议处理程序的对象。 MAPI URL 采用 Unicode 编码，并具有以下格式： 
  
`Mapi://SID/StoreDisplayName ($HashNumber)/StoreType/FolderNameA/…/FolderNameN/[EntryIDEncoded[/at=AttachIDEncoded:FileName]]`

下表介绍了典型 URL 的各个部分。

|Part | 说明|
|:----|:-----------|  
|*SID* |当前用户的安全标识符。| 
|*StoreDisplayName* |一个字符串，显示名称该存储区上的用户名称。|
|*HashNumber* |以十六进制表示形式表示的 **DWORD，** 它基于存储条目 ID 或存储映射签名计算。 此值存储在注册表中，稍后将用于标识 MAPI 协议处理程序中的存储。<br/><br/>此数字必须以最大程度减少与其他存储冲突的方式计算。 有关 Microsoft Outlook计算哈希数的算法，请参阅 Algorithm to [Calculate the Store Hash Number](algorithm-to-calculate-the-store-hash-number.md)。|
|*StoreType* |一个数字，标识包含要编制索引的对象的存储区的类型。 可能值包括：<br/>- 0 - 默认存储。<br/><br/>- 1 - 委托存储，用于本地缓存的委托项。<br/><br/>- 2 - 公用文件夹，用于公用文件夹收藏夹。<br/><br/>**注意**：如果正在对存储进行爬网而不是推送，则使用的值是字符 *X*。| 
|*FolderNameA/.../FolderNameN* |从文件夹或邮件IPM_SUBTREE根目录的路径。 例如，"收件箱"下的 **"** 系列"文件夹中 **的邮件** 具有 **此参数的"收件箱/** 系列"。 |
|*EntryIDEncoded* |编码为 Unicode 字符串的项的 MAPI 条目 ID。 请参阅以下"特殊字符"部分，了解如何对特定特殊字符进行编码。 有关对条目 ID 进行编码的算法详细信息，请参阅对条目 ID 和附件 ID 进行编码 [的算法](algorithm-to-encode-entry-ids-and-attachment-ids.md)。<br/><br/>**注意**：当以文本方式查看时，此编码条目 ID 显示为随机的 Hangul 字符或方框，以与算法一致性，具体取决于可用字体。  |
|*AttachIDEncoded* |编码为 Unicode 字符串的附件 ID。 请参阅以下"特殊字符"部分，了解如何对特定特殊字符进行编码。 有关对条目 ID 进行编码的算法详细信息，请参阅对条目 ID 和附件 ID 进行编码 [的算法](algorithm-to-encode-entry-ids-and-attachment-ids.md)。<br/><br/>**注意**：当以文本方式查看时，此编码条目 ID 显示为随机的 Hangul 字符或方框，以与算法一致性，具体取决于可用字体。 |
|*FileName* |附件文件的名称，如邮件中显示。|
    
## <a name="examples-of-mapi-urls"></a>MAPI URL 示例

下面是 MAPI URL 的一些示例。
  
- 文件夹的 MAPI URL： 
    
  `mapi://S-1-5-21-2127521184-1604012920-1887927527-71418/Mailbox - Some User ($be19928f)/2/Office`
    
- 邮件的 MAPI URL： 
    
  `mapi://S-1-5-21-2127521184-1604012920-1887927527-71418/Mailbox - Some User ($484efb89)/0/Calendar/곯가가가걍걝걌곌겷걢곒갑겛개가검걟곔걙곾걤곂갠가`
    
- 附件的 MAPI URL： 
    
  `mapi://S-1-5-21-2127521184-1604012920-1887927527-71418/Mailbox - Some User ($484efb89)/0/Inbox/곯가가가걍걝걌곌겷걢곒갑겛개가검걟곔걙곾간곷갦가/at=겅걋각가:somefile.txt`
    
## <a name="special-characters"></a>特殊字符

如果某些字符出现在邮件或附件中，则进行编码。 下面显示了在 MAPI URL 中对哪些字符进行编码：
  
- % > %25
    
- / > %2F 
    
- \ > %5C 
    
- \* > %2A 
    
- ? > %3F 
    
## <a name="blob-associated-with-each-mapi-url"></a>与每个 MAPI URL 关联的 Blob

为要编制索引的对象推送 MAPI URL 时，存储提供程序还会创建二进制大型对象 (BLOB) ，其中包含 MAPI 协议处理程序的某些信息。 存储提供程序将此 BLOB 与每个 MAPI URL 关联，并将它在将 MAPI URL 推送到索引器时发送。 BLOB 的格式如下： 
  
```cpp
DWORD  dwVersion
DWORD  dwFlags
ULONG  cbProfileName
WCHAR  wszProfileName
ULONG  cbProviderItemID
WCHAR  wszProviderItemID
```

存储提供程序必须按所示顺序将这些值写入 BLOB。 下表介绍了 BLOB 的每个字段。

|Part | 说明|
|:----|:-----------|  
|*dwVersion* |这是要发送的数据的版本。 当前此值为 1。|
|*dwFlags* |保留供以后使用。 当前此值应为 0。|
|*cbProfileName* |配置文件名称的大小（以字节为单位）。 此信息对于 MAPI 协议处理程序了解在索引项目时将使用哪个配置文件非常有用。|
|*wszProfileName* |包含配置文件名称的以 Null 结尾的 Unicode 字符串。|
|*cbProviderItemID* |提供程序项 ID 的大小（以字节为单位）。 存储提供程序应仅发送文件夹的提供程序项目 ID，以防止打开其他文件夹获取此信息。|
|*wszProviderItemID* |以 Null 结尾的 Unicode 字符串，其提供程序项 ID 唯一标识存储区中的项。|
    
## <a name="see-also"></a>另请参阅

- [关于Notification-Based存储索引](about-notification-based-store-indexing.md)
- [MAPI 常量](mapi-constants.md)

