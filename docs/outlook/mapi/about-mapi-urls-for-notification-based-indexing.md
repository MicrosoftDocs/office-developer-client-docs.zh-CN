---
title: 关于基于通知的索引的 MAPI URL
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: 9cb35f0a-267e-2d85-1701-02d52578a0b8
description: 上次修改时间： 2011 年 11 月 8 日
ms.openlocfilehash: 27ad80b9eca8332beeda147a8b2b4204f9f1cd38
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774462"
---
# <a name="about-mapi-urls-for-notification-based-indexing"></a>关于基于通知的索引的 MAPI URL

**适用于**： Outlook 
  
当存储提供程序通知对象是供索引编制索引器时，它将生成一个唯一标识到 MAPI 协议处理程序的对象的 MAPI URL。 MAPI Url 在 Unicode 中编码和具有以下格式： 
  
`Mapi://SID/StoreDisplayName ($HashNumber)/StoreType/FolderNameA/…/FolderNameN/[EntryIDEncoded[/at=AttachIDEncoded:FileName]]`

下表介绍了典型的 URL 的各个部分。

|部分 | 说明|
|:----|:-----------|  
|*SID* |当前用户的安全标识符。| 
|*StoreDisplayName* |一个字符串，该存储指定用户的显示名称。|
|*HashNumber* |在计算的十六进制表示一个**DWORD**基于存储条目 ID 或存储映射签名。 此值存储在注册表，并且将用于更高版本的 MAPI 协议处理程序中存储的标识。<br/><br/>此号码必须与其他存储将最小化冲突的方式计算。 Microsoft Outlook 用来计算的哈希算法，请参阅[要计算的存储哈希算法](algorithm-to-calculate-the-store-hash-number.md)。|
|*StoreType* |一个数字，标识包含要编制索引的对象的存储区的类型。 可能值如下所示：<br/>-0-默认存储。<br/><br/>-1-代理存储区，用于在本地缓存的委托项。<br/><br/>-2-公用文件夹，用于公用文件夹收藏夹。<br/><br/>**注意**： 如果存储区进行爬网而不是推送，使用的值是*X*的字符。| 
|*FolderNameA/.../FolderNameN* |从 IPM_SUBTREE 根到邮件的文件夹的路径。 例如，在**收件箱**下的**系列**文件夹中的邮件的**收件箱/系列**有此参数。 |
|*EntryIDEncoded* |MAPI 编码为的 Unicode 字符串项的条目 ID。 请参阅下的一节"特殊字符"有关如何对某些特殊字符进行编码。 有关算法进行编码的条目 ID 的详细信息，请参阅[到编码条目 Id 和附件 Id 的算法](algorithm-to-encode-entry-ids-and-attachment-ids.md)。<br/><br/>**注意**： 时查看以文本形式，这编码的条目 ID 显示为随机朝鲜文字符或依照的算法，具体取决于可用字体的框。  |
|*AttachIDEncoded* |附件 ID 编码为的 Unicode 字符串。 请参阅下的一节"特殊字符"有关如何对某些特殊字符进行编码。 有关算法进行编码的条目 ID 的详细信息，请参阅[到编码条目 Id 和附件 Id 的算法](algorithm-to-encode-entry-ids-and-attachment-ids.md)。<br/><br/>**注意**： 时查看以文本形式，这编码的条目 ID 显示为随机朝鲜文字符或依照的算法，具体取决于可用字体的框。 |
|*FileName* |附件名称的文件，在邮件中所示。|
    
## <a name="examples-of-mapi-urls"></a>MAPI Url 的示例

以下是一些示例的 MAPI Url。
  
- MAPI 的文件夹的 URL: 
    
  `mapi://S-1-5-21-2127521184-1604012920-1887927527-71418/Mailbox - Some User ($be19928f)/2/Office`
    
- 邮件的 MAPI URL: 
    
  `mapi://S-1-5-21-2127521184-1604012920-1887927527-71418/Mailbox - Some User ($484efb89)/0/Calendar/곯가가가걍걝걌곌겷걢곒갑겛개가검걟곔걙곾걤곂갠가`
    
- MAPI 的附件的 URL: 
    
  `mapi://S-1-5-21-2127521184-1604012920-1887927527-71418/Mailbox - Some User ($484efb89)/0/Inbox/곯가가가걍걝걌곌겷걢곒갑겛개가검걟곔걙곾간곷갦가/at=겅걋각가:somefile.txt`
    
## <a name="special-characters"></a>特殊字符

如果它们出现在邮件或附件，某些字符进行编码。 下面显示 MAPI URL 中的哪些字符编码：
  
- %> 25%
    
- / > %2f 
    
- \ > %5 C 
    
- \*> %2a 
    
- ? > %3f 
    
## <a name="blob-associated-with-each-mapi-url"></a>每个 MAPI URL 相关联的 blob

时将推送对象 MAPI URL 编制索引，存储提供程序还创建包含 MAPI 协议处理程序的特定信息二进制大型对象 (BLOB)。 存储提供程序将此 BLOB 与每个 MAPI URL 相关联，并将其发送时将 MAPI URL 推送到索引器。 BLOB 的格式如下所示： 
  
```cpp
DWORD  dwVersion
DWORD  dwFlags
ULONG  cbProfileName
WCHAR  wszProfileName
ULONG  cbProviderItemID
WCHAR  wszProviderItemID
```

存储提供程序必须将这些值写入显示的顺序 BLOB。 下表描述了各个字段的 BLOB。

|部分 | 说明|
|:----|:-----------|  
|*dwVersion* |这是发送的数据的版本。 当前此值为 1。|
|*dwFlags* |保留以备今后使用。 当前此值应为 0。|
|*cbProfileName* |配置文件名称，以字节为单位的大小。 此信息可用于 MAPI 协议处理程序，以了解索引项时要使用哪个配置文件。|
|*wszProfileName* |空结尾 Unicode 字符串，包含的配置文件名称。|
|*cbProviderItemID* |提供程序项目 ID，以字节为单位的大小。 存储提供程序应发送仅提供程序项目 ID 为文件夹，以防止打开其他文件夹以获取此信息。|
|*wszProviderItemID* |提供程序项目 id 唯一标识存储区中的项目的空结尾 Unicode 字符串。|
    
## <a name="see-also"></a>另请参阅

- [关于基于通知的存储区索引](about-notification-based-store-indexing.md)
- [MAPI 常量](mapi-constants.md)

