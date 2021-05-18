---
title: 查找 POP3 帐户的邮件下载历史记录
manager: soliver
ms.date: 09/17/2015
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 90a51150-5c2c-4d5b-8717-5dacc8532744
description: 本主题介绍邮件客户端如何访问 PidTagAttachDataBinary 属性，获取 POP3 帐户的邮件下载历史记录。
ms.openlocfilehash: ae12a044098aa4f42e1c2e5936e82da3d7a128dd
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32321873"
---
# <a name="locating-the-message-download-history-for-a-pop3-account"></a>查找 POP3 帐户的邮件下载历史记录

本主题介绍邮件客户端如何访问 [PidTagAttachDataBinary](https://msdn.microsoft.com/library/3b0a8b28-863e-4b96-a4c0-fdb8f40555b9%28Office.15%29.aspx) 属性，获取 POP3 帐户的邮件下载历史记录。 

<a name="OL15Con_AuxRef_LocatingMsgsUIDLHistory_WhyGetUIDLHistory"> </a>

## <a name="why-get-the-message-download-history"></a>为什么获取邮件下载历史记录？

post Office Protocol (POP) provider for Outlook 允许用户检索和下载其本地设备上的新电子邮件，并随后在邮件服务器上保留或删除这些电子邮件。 当邮件客户端检查是否下载新邮件时，它必须能够仅识别并下载该收件箱的新邮件。 邮件客户端通过首先使用 UIDL (唯一 ID 列表) 命令来这样做，该命令获取曾经传递到该收件箱的每封邮件的映射，该邮件会传递到 UID (唯一标识符) 。 客户端还获取该客户端上的收件箱已下载或删除的邮件的邮件下载历史记录。 然后，客户端可以使用消息 UID 映射和下载历史记录，将历史记录中不存在的消息标识为新消息，因此应下载这些消息。
  
若要获取收件箱的邮件下载历史记录，
  
- 按照本主题中的步骤查找 **PidTagAttachDataBinary** 属性，该属性包含采用特定格式的二进制大型对象 (BLOB) 中的历史记录。 
    
- 继续分析 [POP3](parsing-the-message-download-history-for-a-pop3-account.md)帐户的邮件下载历史记录，该历史记录描述如何分析此 BLOB 以标识已为此收件箱下载或删除的邮件。
    
## <a name="core-concepts-to-know-for-locating-the-message-download-history"></a>了解用于定位邮件下载历史记录的核心概念

收件箱的邮件下载历史记录存储在二进制 MAPI 属性 **PidTagAttachDataBinary** 中，位于收件箱中隐藏邮件的附件中。 表 1 显示了帮助您了解如何查找邮件下载历史记录的概念资源。
  
**表 1. 核心概念**

|**文章标题**|**说明**|
|:-----|:-----|
|[MAPI 隐藏文件夹](https://msdn.microsoft.com/library/8b3b9c80-f7f4-4f37-bd6b-323469d020f1%28Office.15%29.aspx) <br/> |MAPI 允许邮件客户端将信息存储在隐藏文件夹和隐藏邮件中。 隐藏文件夹位于 MAPI 文件夹的关联部分，通常包含用户不可见和不可操作的信息。 客户端决定将格式和内容存储在隐藏文件夹中的隐藏邮件中。  <br/> |
|[MAPI 邮件](https://msdn.microsoft.com/library/417c113f-bd98-4515-85d1-09db7fc3a227%28Office.15%29.aspx) <br/> |MAPI 将邮件存储在文件夹中，既可以在客户端用户可见的标准 IPM 子树中，也可以存储在子树外部且对用户不可见。 邮件可以有附加数据存储在附件中，可以是文件、其他邮件或 OLE 对象。 对于邮件下载历史记录，历史记录存储在附加到另一个隐藏邮件的邮件的属性中。  <br/> |
|[邮件属性概述](https://msdn.microsoft.com/library/447f54de-9f0d-4f73-89b6-bed9cfea9c15%28Office.15%29.aspx) <br/> |当客户端在邮件中存储信息时，实际上将该信息存储在邮件的属性中。 MAPI 支持许多属性（其中一些属性始终存在，并且可通过客户端设置，其他属性是可选的）并且客户端无法期望它们可用或设置为有效值。 邮件下载历史记录存储在隐藏邮件附件的 **PidTagAttachDataBinary** 属性中。  <br/> |
|[MAPI 配置文件](https://msdn.microsoft.com/library/493c87a4-317d-47ec-850b-342cac59594b%28Office.15%29.aspx) <br/> |在会话的登录时，邮件客户端选择描述要使用的提供程序和服务的配置文件。 配置文件分为多个部分，其中包含属性。 特别是 [，PidTagSearchKey](https://msdn.microsoft.com/library/fcab369a-a1f4-4425-a272-e35046914a4d%28Office.15%29.aspx) (PR_SEARCH_KEY **)** 和 [PidTagProfileName](https://msdn.microsoft.com/library/13ca726d-ae7a-4da9-9c8e-3db3c479f839%28Office.15%29.aspx) (PR_PROFILE_NAME) 始终存在。  配置文件的搜索键在所有配置文件中是唯一的，并存储在由 mapIGUID 中定义的 **MUID_PROFILE_INSTANCE** (标识的配置文件节中。H) 。 使用 [IMAPISession：：OpenProfileSection](https://msdn.microsoft.com/library/e2757028-27e7-4fc0-9674-e8e30737ef1d%28Office.15%29.aspx) 打开分区，并使用 [IMAPIProp：：GetProps](https://msdn.microsoft.com/library/1c7a9cd2-d765-4218-9aee-52df1a2aae6c%28Office.15%29.aspx) 获取属性值。  <br/> |
|[内容表](https://msdn.microsoft.com/library/7b8efb4e-b5be-41b8-81bb-9aa1da421433%28Office.15%29.aspx) <br/> |邮件存储提供程序会为文件夹实现内容表。 对于文件夹的关联部分中的隐藏邮件，邮件存储提供程序支持关联的内容表，客户端可以使用 [IMAPIContainer：：GetContentsTable](https://msdn.microsoft.com/library/88c7a666-875d-473a-b126-dbbb7009f7d9%28Office.15%29.aspx) 方法返回指向关联内容表的指针。  <br/> |
|[关于限制](https://msdn.microsoft.com/library/e119fa20-08b8-4c8d-93fc-56037220890d%28Office.15%29.aspx) <br/> [限制类型](https://msdn.microsoft.com/library/0d3bd58b-7100-4117-91ac-27139715c85b%28Office.15%29.aspx) <br/> [构建限制](https://msdn.microsoft.com/library/12abbd8c-f825-493e-af42-344371d9658e%28Office.15%29.aspx) <br/> [示例限制代码](https://msdn.microsoft.com/library/9b82097c-dbd6-4ba0-a6cb-292301f9402b%28Office.15%29.aspx) <br/> |在 MAPI 中，客户端可以使用限制来筛选内容表，以搜索表示将特定属性设置为特定值的邮件的行。 限制通过使用 [SRestriction](https://msdn.microsoft.com/library/c12b4409-da6f-480b-87af-1e5baea2e8bd%28Office.15%29.aspx) 数据结构定义，其中可以包含一组更专业的限制结构。 [IMAPITable：：FindRow](https://msdn.microsoft.com/library/6511368c-9777-497e-9eea-cf390c04b92e%28Office.15%29.aspx)方法应用限制并检索表中符合限制条件的第一行。  <br/> |
|[关于注册用于索引的存储区](https://msdn.microsoft.com/library/dd2aa06a-96e8-1291-18b5-fc3c40b74e4d%28Office.15%29.aspx) <br/> |使用 [PidTagStoreProvider](https://msdn.microsoft.com/library/6f6cc66f-a08e-4f8e-b33a-d3674319248e%28Office.15%29.aspx) (PR_MDB_PROVIDER **)** 属性验证存储提供程序的类型。 例如，若要验证存储区是否是 Exchange 存储 **，PidTagStoreProvider** 属性应返回由常量 **pbExchangeProviderPrimaryUserGuid** 表示的值，该值在公共头文件 edkmdb.h 中定义。  <br/> |
   
## <a name="locating-the-appropriate-hidden-message-and-attachment"></a>找到相应的隐藏邮件和附件

既然我们知道收件箱的邮件下载历史记录位于隐藏邮件附件的 **PidTagAttachDataBinary** 属性中，找到相应隐藏邮件的适当附件的过程将涉及以下过程： 
  
1. [查找相应的隐藏邮件](#OL15Con_AuxRef_LocatingMsgsUIDLHistory_FindHiddenMsg)
    
2. [查找隐藏邮件的适当附件](#OL15Con_AuxRef_LocatingMsgsUIDLHistory_FindAttachment)
    
3. [访问邮件附件的 PidTagAttachDataBinary 属性](#OL15Con_AuxRef_LocatingMsgsUIDLHistory_AccessProp)

<a name="OL15Con_AuxRef_LocatingMsgsUIDLHistory_FindHiddenMsg"> </a>

### <a name="find-the-appropriate-hidden-message"></a>查找相应的隐藏邮件

1. 从配置文件（在 (PR_SEARCH_KEY) 配置文件部分获取 [PidTagSearchKey](https://msdn.microsoft.com/library/fcab369a-a1f4-4425-a272-e35046914a4d%28Office.15%29.aspx)属性 **MUID_PROFILE_INSTANCE。** 
    
2. 通过调用 **IMAPIContainer：：GetContentsTable 打开收件箱文件夹的关联内容**。
    
3. 基于 [PidTagConversationKey](https://msdn.microsoft.com/library/52c97d6c-7f4b-4522-aeac-0c1ed8475952%28Office.15%29.aspx) (**PR_CONVERSATION_KEY** **) 、PidTagSearchKey** (**PR_SEARCH_KEY**) 和 [PidTagMessageClass](https://msdn.microsoft.com/library/1e704023-1992-4b43-857e-0a7da7bc8e87%28Office.15%29.aspx) (**PR_MESSAGE_CLASS)** 属性创建限制，以获取包含收件箱的关联内容中所有隐藏邮件的表。 下面是从"定位 [POP3 UIDL](https://blogs.msdn.com/b/stephen_griffin/archive/2012/12/03/locating-the-pop3-uidl-history.aspx)历史记录"中提取的限制示例。
    
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

4. 从表中，使用 **IMAPITable：：FindRow 查找隐藏的消息**。
    
5. 如果步骤 4 未能找到隐藏邮件，请更改限制以使用 **PidTagSearchKey** (**PR_SEARCH_KEY**) 而不是 **PidTagConversationKey，** 如下所示：
    
   ```cpp
    rgRes[1].res.resProperty.ulPropTag = rgProps[0].ulPropTag = PR_SEARCH_KEY;
   ```

6. 使用 **IMAPITable：：FindRow 查找隐藏的消息**。 
    
7. 如果步骤 6 失败，请更改对 [使用 PidTagSubject](https://msdn.microsoft.com/library/aa7ba4d9-c5e0-4ce7-a34e-65f675223bc9%28Office.15%29.aspx) (**PR_SUBJECT)** 等于以下值的限制 (使用样式替换来简洁  `printf`) 。 
    
   ```cpp
    "Outlook Message Manager (%s) (KEY: %s)", PR_PROFILE_NAME, HexFromBin(PR_SEARCH_KEY)
   ```

8. 使用 **IMAPITable：：FindRow 查找隐藏的消息**。
    
9. 如果运行的是 Outlook 2010 或更高版本，请分别为 **PidTagProfileName** (**PR_PROFILE_NAME**) 和 **PidTagSearchKey** (PR_SEARCH_KEY **)** 使用以下值。
    
   ```cpp
    CHAR g_szGeneralKey[] = "General Key"; 
    const SBinary g_binGeneralKey = {sizeof(g_szGeneralKey), (LPBYTE)g_szGeneralKey};
   ```

   执行步骤 3 至 8。 如果找不到邮件，请回退到原始步骤 3 至 8。
    
10. 打开在步骤 4、6 或 8 中找到的隐藏邮件。

<a name="OL15Con_AuxRef_LocatingMsgsUIDLHistory_FindAttachment"> </a>

### <a name="find-the-appropriate-attachment-of-the-hidden-message"></a>查找隐藏邮件的适当附件

因为隐藏邮件可能具有多个附件，所以按以下顺序查找相应的附件。
  
> [!NOTE]
> 此过程再次使用  `printf` 样式替换，以简洁。 

1. 查找其 [PidTagAttachLongFilename](https://msdn.microsoft.com/library/83b69e8f-0b5a-4992-b5b8-160d3bdfa22a%28Office.15%29.aspx) (PR_ATTACH_LONG_FILENAME **)** 与用户配置文件中指定的以下字符串相匹配的附件，其中 是用户的 SMTP 地址。 `szEmailAddress` . 
    
   ```cpp
    "BlobPOP%s", szEmailAddress
   ```

2. 查找其[PidTagAttachFilename](https://msdn.microsoft.com/library/cbf34dd6-7733-47f6-9c41-9d82656ca9dc%28Office.15%29.aspx) (PR_ATTACH_FILENAME) 匹配"BlobPOP%s"的附件 `szEmailAddress` 。
    
3. 查找其 [PidTagDisplayName](https://msdn.microsoft.com/library/bd094e00-5c60-4bb3-9a45-b943fab52876%28Office.15%29.aspx) **(PR_DISPLAY_NAME)** 匹配"BlobPOP%s"的附件  `szEmailAddress` 。
    
4. 查找其 **PidTagAttachFilename** (PR_ATTACH_FILENAME) 匹配"Blob%.8x"的附件，其中 来自 `dwAcctUID` `dwAcctUID` [PROP_ACCT_MINI_UID](prop_acct_mini_uid.md)。 可以使用 [IOlkAccount：：GetProp](iolkaccount-getprop.md)方法访问 PROP_ACCT_MINI_UID **属性。** 

<a name="OL15Con_AuxRef_LocatingMsgsUIDLHistory_AccessProp"> </a>

### <a name="access-the-pidtagattachdatabinary-property-of-the-message-attachment"></a>访问邮件附件的 PidTagAttachDataBinary 属性

找到隐藏邮件的适当邮件附件后，使用 **IMAPIProp：：GetProps** 读取附件的 **PidTagAttachDataBinary** 属性。 

<a name="OL15Con_AuxRef_LocatingMsgsUIDLHistory_NextSteps"> </a>

## <a name="next-steps"></a>后续步骤

您从本主题中了解到了如何查找 POP3 邮件客户端收件箱的邮件下载历史记录。 请参阅 [分析 POP3](parsing-the-message-download-history-for-a-pop3-account.md) 帐户的邮件下载历史记录，了解如何分析此历史记录以标识已下载或删除收件箱的邮件。 

<a name="OL15Con_AuxRef_LocatingMsgsUIDLHistory_AdditionalRsc"> </a>

## <a name="see-also"></a>另请参阅

- [管理 POP3 帐户的邮件下载](managing-message-downloads-for-pop3-accounts.md)   
- [分析 POP3 帐户的邮件下载历史记录](parsing-the-message-download-history-for-a-pop3-account.md)
- [定位 POP3 UIDL 历史记录](https://blogs.msdn.com/b/stephen_griffin/archive/2012/12/03/locating-the-pop3-uidl-history.aspx)
    

