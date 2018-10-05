---
title: 查找 POP3 帐户的邮件下载历史记录
manager: soliver
ms.date: 09/17/2015
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 90a51150-5c2c-4d5b-8717-5dacc8532744
description: 本主题介绍如何邮件客户端可以访问 PidTagAttachDataBinary 属性获取 POP3 帐户的消息下载历史记录。
ms.openlocfilehash: ae12a044098aa4f42e1c2e5936e82da3d7a128dd
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25399550"
---
# <a name="locating-the-message-download-history-for-a-pop3-account"></a>查找 POP3 帐户的邮件下载历史记录

本主题介绍如何邮件客户端可以访问[PidTagAttachDataBinary](https://msdn.microsoft.com/library/3b0a8b28-863e-4b96-a4c0-fdb8f40555b9%28Office.15%29.aspx)属性获取 POP3 帐户的消息下载历史记录。 

<a name="OL15Con_AuxRef_LocatingMsgsUIDLHistory_WhyGetUIDLHistory"> </a>

## <a name="why-get-the-message-download-history"></a>为什么收到的消息下载历史记录？

Outlook 邮局协议 (POP) 提供程序允许用户检索并在其本地设备上的新电子邮件下载并随后保留或删除这些邮件服务器上的电子邮件。 当邮件客户端检查新邮件，若要下载时，它具有能够识别和仅下载新邮件的收件箱。 邮件客户端首先使用 UIDL （唯一 ID 列出） 命令，获取以往任何时候都已传递给为唯一标识符 (UID) 的收件箱每封邮件的地图来达到此目的。 客户端还获取的已下载或删除该客户端上的收件箱邮件的消息下载历史记录。 使用邮件 UID 地图和下载历史记录，客户端可以然后确定不存在这些消息在历史记录，通过新建，因此，应下载。
  
若要获取的收件箱的消息下载历史记录：
  
- 按照本主题查找**PidTagAttachDataBinary**属性，其中包含中二进制大型对象 (BLOB) 的特定格式的历史记录中的步骤。 
    
- 继续[分析 POP3 帐户的消息下载历史记录](parsing-the-message-download-history-for-a-pop3-account.md)，其中介绍了如何分析此 BLOB 标识的已下载或删除的收件箱邮件。
    
## <a name="core-concepts-to-know-for-locating-the-message-download-history"></a>要了解的查找邮件的核心概念下载历史记录

收件箱的消息下载历史记录存储在二进制 MAPI 属性，可**PidTagAttachDataBinary**，在收件箱中的隐藏邮件的附件。 表 1 显示了为帮助您了解如何找到的消息下载历史记录的概念的资源。
  
**表 1. 核心概念**

|**文章标题**|**说明**|
|:-----|:-----|
|[MAPI 隐藏文件夹](https://msdn.microsoft.com/library/8b3b9c80-f7f4-4f37-bd6b-323469d020f1%28Office.15%29.aspx) <br/> |MAPI 允许邮件客户端中隐藏的文件夹和隐藏的邮件存储信息。 隐藏的文件夹中的关联部分的 MAPI 文件夹，通常包含对不可见的信息而不用户操作。 客户端决定的格式和内容存储在隐藏的文件夹中的隐藏邮件。  <br/> |
|[MAPI 邮件](https://msdn.microsoft.com/library/417c113f-bd98-4515-85d1-09db7fc3a227%28Office.15%29.aspx) <br/> |MAPI 中对用户的客户端，或外部子树和用户看不到可见的标准 IPM 子树的文件夹中存储的邮件。 消息可以具有存储在附件，可以是一个文件，另一条消息或 OLE 对象的窗体中的其他数据。 对于消息下载历史记录，历史记录存储在一条消息，附加到另一个隐藏邮件的属性。  <br/> |
|[邮件属性概述](https://msdn.microsoft.com/library/447f54de-9f0d-4f73-89b6-bed9cfea9c15%28Office.15%29.aspx) <br/> |当客户端将信息存储在一条消息时，它将实际属性中的邮件存储的信息。 MAPI 支持许多属性 — 某些始终存在，可以通过客户端设置、 都是可选的其他人 — 和客户端无法所期望可用或设置为有效的值。 隐藏邮件的附件的**PidTagAttachDataBinary**属性中存储的消息下载历史记录。  <br/> |
|[MAPI 配置文件](https://msdn.microsoft.com/library/493c87a4-317d-47ec-850b-342cac59594b%28Office.15%29.aspx) <br/> |在会话中的登录时，邮件客户端选择介绍要使用的提供程序和服务的配置文件。 一个配置文件分为包含属性的部分。 具体而言， [PidTagSearchKey](https://msdn.microsoft.com/library/fcab369a-a1f4-4425-a272-e35046914a4d%28Office.15%29.aspx) (**PR_SEARCH_KEY**) 和[PidTagProfileName](https://msdn.microsoft.com/library/13ca726d-ae7a-4da9-9c8e-3db3c479f839%28Office.15%29.aspx) (**PR_PROFILE_NAME**) 属性始终存在。 配置文件的搜索关键字唯一所有配置文件，并存储在配置文件部分的由**MUID_PROFILE_INSTANCE** （其中 MAPIGUID 中定义。H)。 使用[IMAPISession::OpenProfileSection](https://msdn.microsoft.com/library/e2757028-27e7-4fc0-9674-e8e30737ef1d%28Office.15%29.aspx)以打开部分，并使用[IMAPIProp::GetProps](https://msdn.microsoft.com/library/1c7a9cd2-d765-4218-9aee-52df1a2aae6c%28Office.15%29.aspx)获取属性值。  <br/> |
|[内容表](https://msdn.microsoft.com/library/7b8efb4e-b5be-41b8-81bb-9aa1da421433%28Office.15%29.aspx) <br/> |消息存储提供程序实现其文件夹的内容表。 对相关部件的文件夹中的隐藏邮件，消息存储提供程序支持的关联的内容表和客户端可以使用[IMAPIContainer::GetContentsTable](https://msdn.microsoft.com/library/88c7a666-875d-473a-b126-dbbb7009f7d9%28Office.15%29.aspx)方法以返回到关联的内容表的指针。  <br/> |
|[关于限制](https://msdn.microsoft.com/library/e119fa20-08b8-4c8d-93fc-56037220890d%28Office.15%29.aspx) <br/> [限制的类型](https://msdn.microsoft.com/library/0d3bd58b-7100-4117-91ac-27139715c85b%28Office.15%29.aspx) <br/> [生成限制](https://msdn.microsoft.com/library/12abbd8c-f825-493e-af42-344371d9658e%28Office.15%29.aspx) <br/> [示例限制代码](https://msdn.microsoft.com/library/9b82097c-dbd6-4ba0-a6cb-292301f9402b%28Office.15%29.aspx) <br/> |MAPI，在客户端可以使用限制筛选内容表格，搜索行表示的某些属性设置为特定值的邮件。 通过使用[SRestriction](https://msdn.microsoft.com/library/c12b4409-da6f-480b-87af-1e5baea2e8bd%28Office.15%29.aspx)数据结构，它可以包含的更多专用限制结构联合定义限制。 [IMAPITable::FindRow](https://msdn.microsoft.com/library/6511368c-9777-497e-9eea-cf390c04b92e%28Office.15%29.aspx)方法应用限制，并检索与限制条件匹配的表中的第一行。  <br/> |
|[关于注册用于建立索引的存储区](https://msdn.microsoft.com/library/dd2aa06a-96e8-1291-18b5-fc3c40b74e4d%28Office.15%29.aspx) <br/> |[PidTagStoreProvider](https://msdn.microsoft.com/library/6f6cc66f-a08e-4f8e-b33a-d3674319248e%28Office.15%29.aspx) (**PR_MDB_PROVIDER**) 属性用于验证存储提供程序的类型。 例如，若要验证是否在 Exchange 存储存储区， **PidTagStoreProvider**属性应返回常量**pbExchangeProviderPrimaryUserGuid**，在公共头文件 edkmdb.h 中定义所表示的值。  <br/> |
   
## <a name="locating-the-appropriate-hidden-message-and-attachment"></a>查找相应的隐藏的邮件和附件

现在，我们了解收件箱的消息下载历史记录处于隐藏邮件的附件的**PidTagAttachDataBinary**属性，以找到相应的适当的隐藏邮件的附件的过程涉及以下过程： 
  
1. [查找相应的隐藏的邮件](#OL15Con_AuxRef_LocatingMsgsUIDLHistory_FindHiddenMsg)
    
2. [查找相应的隐藏邮件的附件](#OL15Con_AuxRef_LocatingMsgsUIDLHistory_FindAttachment)
    
3. [访问邮件附件的 PidTagAttachDataBinary 属性](#OL15Con_AuxRef_LocatingMsgsUIDLHistory_AccessProp)

<a name="OL15Con_AuxRef_LocatingMsgsUIDLHistory_FindHiddenMsg"> </a>

### <a name="find-the-appropriate-hidden-message"></a>查找相应的隐藏的邮件

1. 在配置文件部分指定**MUID_PROFILE_INSTANCE**从配置文件，获取[PidTagSearchKey](https://msdn.microsoft.com/library/fcab369a-a1f4-4425-a272-e35046914a4d%28Office.15%29.aspx) (**PR_SEARCH_KEY**) 属性。
    
2. 通过调用**IMAPIContainer::GetContentsTable**打开相关联的收件箱文件夹内容。
    
3. 创建基于[PidTagConversationKey](https://msdn.microsoft.com/library/52c97d6c-7f4b-4522-aeac-0c1ed8475952%28Office.15%29.aspx) (**PR_CONVERSATION_KEY**)、 **PidTagSearchKey** (**PR_SEARCH_KEY**) 和[PidTagMessageClass](https://msdn.microsoft.com/library/1e704023-1992-4b43-857e-0a7da7bc8e87%28Office.15%29.aspx) (**PR_MESSAGE_CLASS**) 属性限制的获取 table包含的收件箱关联内容中的所有隐藏的消息。 下面是限制的从[查找 POP3 UIDL 历史记录](https://blogs.msdn.com/b/stephen_griffin/archive/2012/12/03/locating-the-pop3-uidl-history.aspx)中提取的示例。
    
   ```cpp
      SRestriction rgRes[3]; 
      SPropValue rgProps[3]; 
      rgRes[0].rt = RES_AND; 
      rgRes[0].res.resAnd.cRes = 2; 
      rgRes[0].res.resAnd.lpRes = &amp;rgRes[1]; 
      rgRes[1].rt = RES_PROPERTY; 
      rgRes[1].res.resProperty.relop = RELOP_EQ; 
      rgRes[1].res.resProperty.ulPropTag = PR_CONVERSATION_KEY; 
      rgRes[1].res.resProperty.lpProp = &amp;rgProps[0]; 
      rgRes[2].rt = RES_PROPERTY; 
      rgRes[2].res.resProperty.relop = RELOP_EQ; 
      rgRes[2].res.resProperty.ulPropTag = PR_MESSAGE_CLASS; 
      rgRes[2].res.resProperty.lpProp = &amp;rgProps[1]; 
      rgProps[0].ulPropTag = PR_CONVERSATION_KEY; 
      rgProps[0].Value.bin = pVals[iSearchKey].Value.bin; // PR_SEARCH_KEY from the profile 
      rgProps[1].ulPropTag = PR_MESSAGE_CLASS; 
      rgProps[1].Value.LPSZ = (LPTSTR)"IPM.MessageManager";
   ```

4. 从表格中，使用**IMAPITable::FindRow**查找隐藏的邮件。
    
5. 如果未能找到的隐藏的邮件步骤 4，更改要使用**PidTagSearchKey** (**PR_SEARCH_KEY**) 而不是**PidTagConversationKey**，，，如下所示的限制：
    
   ```cpp
    rgRes[1].res.resProperty.ulPropTag = rgProps[0].ulPropTag = PR_SEARCH_KEY;
   ```

6. 查找使用**IMAPITable::FindRow**隐藏的邮件。 
    
7. 如果第 6 步失败，更改要使用[PidTagSubject](https://msdn.microsoft.com/library/aa7ba4d9-c5e0-4ce7-a34e-65f675223bc9%28Office.15%29.aspx) (**PR_SUBJECT**) 等于以下值的限制 (使用如下所示`printf`样式替换为简便起见)。 
    
   ```cpp
    "Outlook Message Manager (%s) (KEY: %s)", PR_PROFILE_NAME, HexFromBin(PR_SEARCH_KEY)
   ```

8. 使用**IMAPITable::FindRow**查找隐藏的邮件。
    
9. 如果您运行的 Outlook 2010 或更高版本，使用以下值**PidTagProfileName** (**PR_PROFILE_NAME**) 和**PidTagSearchKey** (**PR_SEARCH_KEY**)，分别。
    
   ```cpp
    CHAR g_szGeneralKey[] = "General Key"; 
    const SBinary g_binGeneralKey = {sizeof(g_szGeneralKey), (LPBYTE)g_szGeneralKey};
   ```

   运行通过步骤 3 至 8。 如果这无法查找一条消息，回退到原始步骤 3 至 8。
    
10. 打开在步骤 4、 6 或 8 中发现的隐藏的邮件。

<a name="OL15Con_AuxRef_LocatingMsgsUIDLHistory_FindAttachment"> </a>

### <a name="find-the-appropriate-attachment-of-the-hidden-message"></a>查找相应的隐藏邮件的附件

因为隐藏的邮件可能有多个附件，查找以下顺序中的相应附件。
  
> [!NOTE]
> 此过程将再次使用`printf`样式为简便起见替换。 

1. 查找的附件其[PidTagAttachLongFilename](https://msdn.microsoft.com/library/83b69e8f-0b5a-4992-b5b8-160d3bdfa22a%28Office.15%29.aspx) (**PR_ATTACH_LONG_FILENAME**) 匹配以下字符串，其中`szEmailAddress`在用户的配置文件中指定的用户的 SMTP 地址。 . 
    
   ```cpp
    "BlobPOP%s", szEmailAddress
   ```

2. 查找的附件其[PidTagAttachFilename](https://msdn.microsoft.com/library/cbf34dd6-7733-47f6-9c41-9d82656ca9dc%28Office.15%29.aspx) (**PR_ATTACH_FILENAME**) 匹配"BlobPOP %s" `szEmailAddress`。
    
3. 查找的附件其[PidTagDisplayName](https://msdn.microsoft.com/library/bd094e00-5c60-4bb3-9a45-b943fab52876%28Office.15%29.aspx) (**PR_DISPLAY_NAME**) 匹配"BlobPOP %s" `szEmailAddress`。
    
4. 查找的附件其**PidTagAttachFilename** (**PR_ATTACH_FILENAME**) 匹配"Blob%.8x" `dwAcctUID`，其中`dwAcctUID`来自[PROP_ACCT_MINI_UID](prop_acct_mini_uid.md)。 您可以使用[IOlkAccount::GetProp](iolkaccount-getprop.md)方法访问**PROP_ACCT_MINI_UID**属性。 

<a name="OL15Con_AuxRef_LocatingMsgsUIDLHistory_AccessProp"> </a>

### <a name="access-the-pidtagattachdatabinary-property-of-the-message-attachment"></a>访问邮件附件的 PidTagAttachDataBinary 属性

找到相应的消息的隐藏邮件的附件后, 使用**IMAPIProp::GetProps**读取的附件的**PidTagAttachDataBinary**属性。 

<a name="OL15Con_AuxRef_LocatingMsgsUIDLHistory_NextSteps"> </a>

## <a name="next-steps"></a>后续步骤

您已从本主题了解如何为 POP3 邮件客户端的收件箱中找到的消息下载历史记录。 请参阅[分析 POP3 帐户的消息下载历史记录](parsing-the-message-download-history-for-a-pop3-account.md)以了解如何解析此历史记录，以确定已下载或删除的收件箱的邮件。 

<a name="OL15Con_AuxRef_LocatingMsgsUIDLHistory_AdditionalRsc"> </a>

## <a name="see-also"></a>另请参阅

- [管理 POP3 帐户的邮件下载](managing-message-downloads-for-pop3-accounts.md)   
- [分析 POP3 帐户的邮件下载历史记录](parsing-the-message-download-history-for-a-pop3-account.md)
- [查找 POP3 UIDL 历史记录](https://blogs.msdn.com/b/stephen_griffin/archive/2012/12/03/locating-the-pop3-uidl-history.aspx)
    

