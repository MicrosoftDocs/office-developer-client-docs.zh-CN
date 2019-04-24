---
title: 查找 POP3 帐户的邮件下载历史记录
manager: soliver
ms.date: 09/17/2015
ms.audience: Developer
ms.topic: overview
localization_priority: Normal
ms.assetid: 90a51150-5c2c-4d5b-8717-5dacc8532744
description: 本主题介绍邮件客户端如何访问 PidTagAttachDataBinary 属性以获取 POP3 帐户的邮件下载历史记录。
ms.openlocfilehash: ae12a044098aa4f42e1c2e5936e82da3d7a128dd
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32321873"
---
# <a name="locating-the-message-download-history-for-a-pop3-account"></a>查找 POP3 帐户的邮件下载历史记录

本主题介绍邮件客户端如何访问[PidTagAttachDataBinary](https://msdn.microsoft.com/library/3b0a8b28-863e-4b96-a4c0-fdb8f40555b9%28Office.15%29.aspx)属性以获取 POP3 帐户的邮件下载历史记录。 

<a name="OL15Con_AuxRef_LocatingMsgsUIDLHistory_WhyGetUIDLHistory"> </a>

## <a name="why-get-the-message-download-history"></a>为什么要获取邮件下载历史记录？

Outlook 的邮局协议 (POP) 提供程序允许用户在其本地设备上检索和下载新的电子邮件, 并随后在邮件服务器上保留或删除这些电子邮件。 当邮件客户端检查要下载的新邮件时, 它必须能够识别和下载该收件箱的新邮件。 邮件客户端首先使用 UIDL (唯一 ID 列表) 命令, 它会获取已传递到该收件箱的每封邮件的唯一标识符 (UID) 的地图。 客户端还会获取邮件下载历史记录, 以了解已为该客户端上的 "收件箱" 下载或删除的邮件。 通过使用邮件 UID 映射和下载历史记录, 客户端可以将历史记录中缺少的那些邮件标识为新的, 因此应下载这些邮件。
  
要获取收件箱的邮件下载历史记录, 请执行以下操作:
  
- 按照本主题中的步骤查找**PidTagAttachDataBinary**属性, 该属性包含二进制大型对象 (BLOB) 中的历史记录, 该属性遵循特定的格式。 
    
- 继续[分析 POP3 帐户的邮件下载历史记录](parsing-the-message-download-history-for-a-pop3-account.md), 其中介绍了如何分析此 BLOB 以标识已为该收件箱下载或删除的邮件。
    
## <a name="core-concepts-to-know-for-locating-the-message-download-history"></a>查找邮件下载历史记录时要了解的核心概念

"收件箱" 的邮件下载历史记录存储在 "收件箱" 中的隐藏邮件附件上的二进制 MAPI 属性**PidTagAttachDataBinary**中。 表1显示了可帮助您了解如何查找邮件下载历史记录的概念的资源。
  
**表 1. 核心概念**

|**文章标题**|**说明**|
|:-----|:-----|
|[MAPI 隐藏文件夹](https://msdn.microsoft.com/library/8b3b9c80-f7f4-4f37-bd6b-323469d020f1%28Office.15%29.aspx) <br/> |MAPI 允许邮件客户端将信息存储在隐藏的文件夹和隐藏的邮件中。 隐藏的文件夹位于 MAPI 文件夹的关联部分中, 并且通常包含不可见且不能由用户操作的信息。 客户端决定要在隐藏文件夹中的隐藏邮件中存储的格式和内容。  <br/> |
|[MAPI 邮件](https://msdn.microsoft.com/library/417c113f-bd98-4515-85d1-09db7fc3a227%28Office.15%29.aspx) <br/> |MAPI 将邮件存储在文件夹中, 无论是对客户端用户可见的标准 IPM 子树中, 还是在子树外部可见且对用户不可见。 邮件可以包含存储在附件中的其他数据, 可以是文件的格式、另一封邮件, 也可以是 OLE 对象。 在邮件下载历史记录的情况下, 历史记录存储在附加到另一个隐藏邮件的邮件的属性中。  <br/> |
|[邮件属性概述](https://msdn.microsoft.com/library/447f54de-9f0d-4f73-89b6-bed9cfea9c15%28Office.15%29.aspx) <br/> |当客户端将信息存储在邮件中时, 它实际上会将信息存储在邮件的属性中。 MAPI 支持许多属性, 一些属性始终存在并且可由客户端设置, 其他属性是可选的, 客户端不会期望它们可用或设置为有效的值。 邮件下载历史记录存储在附件的**PidTagAttachDataBinary**属性中, 并指向隐藏的邮件。  <br/> |
|[MAPI 配置文件](https://msdn.microsoft.com/library/493c87a4-317d-47ec-850b-342cac59594b%28Office.15%29.aspx) <br/> |在会话中登录时, 邮件客户端将选择描述要使用的提供程序和服务的配置文件。 配置文件分为包含属性的部分。 特别是, [PidTagSearchKey](https://msdn.microsoft.com/library/fcab369a-a1f4-4425-a272-e35046914a4d%28Office.15%29.aspx) (**PR_SEARCH_KEY**) 和[PidTagProfileName](https://msdn.microsoft.com/library/13ca726d-ae7a-4da9-9c8e-3db3c479f839%28Office.15%29.aspx) (**PR_PROFILE_NAME**) 属性始终存在。 配置文件的搜索键在所有配置文件中都是唯一的, 并存储在由**MUID_PROFILE_INSTANCE**标识的 profile 部分中 (在 MAPIGUID 中定义)。H)。 使用[IMAPISession:: OpenProfileSection](https://msdn.microsoft.com/library/e2757028-27e7-4fc0-9674-e8e30737ef1d%28Office.15%29.aspx)打开节, 并使用[IMAPIProp:: GetProps](https://msdn.microsoft.com/library/1c7a9cd2-d765-4218-9aee-52df1a2aae6c%28Office.15%29.aspx)获取属性值。  <br/> |
|[内容表](https://msdn.microsoft.com/library/7b8efb4e-b5be-41b8-81bb-9aa1da421433%28Office.15%29.aspx) <br/> |邮件存储提供程序实现其文件夹的内容表格。 对于文件夹的相关部分中的隐藏邮件, 邮件存储提供程序支持关联的内容表, 并且客户端可以使用[IMAPIContainer:: GetContentsTable](https://msdn.microsoft.com/library/88c7a666-875d-473a-b126-dbbb7009f7d9%28Office.15%29.aspx)方法返回指向关联的内容表的指针。  <br/> |
|[关于限制](https://msdn.microsoft.com/library/e119fa20-08b8-4c8d-93fc-56037220890d%28Office.15%29.aspx) <br/> [限制类型](https://msdn.microsoft.com/library/0d3bd58b-7100-4117-91ac-27139715c85b%28Office.15%29.aspx) <br/> [建立限制](https://msdn.microsoft.com/library/12abbd8c-f825-493e-af42-344371d9658e%28Office.15%29.aspx) <br/> [示例限制代码](https://msdn.microsoft.com/library/9b82097c-dbd6-4ba0-a6cb-292301f9402b%28Office.15%29.aspx) <br/> |在 MAPI 中, 客户端可以使用限制来筛选内容表, 以搜索表示特定属性设置为特定值的邮件的行。 限制是通过使用[SRestriction](https://msdn.microsoft.com/library/c12b4409-da6f-480b-87af-1e5baea2e8bd%28Office.15%29.aspx)数据结构 (可包含更专用的限制结构的联合) 定义的。 [IMAPITable:: FindRow](https://msdn.microsoft.com/library/6511368c-9777-497e-9eea-cf390c04b92e%28Office.15%29.aspx)方法应用限制, 并检索符合限制条件的表格中的第一行。  <br/> |
|[关于注册用于编制索引的存储](https://msdn.microsoft.com/library/dd2aa06a-96e8-1291-18b5-fc3c40b74e4d%28Office.15%29.aspx) <br/> |使用[PidTagStoreProvider](https://msdn.microsoft.com/library/6f6cc66f-a08e-4f8e-b33a-d3674319248e%28Office.15%29.aspx) (**PR_MDB_PROVIDER**) 属性验证存储提供程序的类型。 例如, 若要验证某个存储是否为 Exchange 存储, **PidTagStoreProvider**属性应返回一个由常量**pbExchangeProviderPrimaryUserGuid**表示的值, 该常量是在公用头文件 edkmdb 中定义的。  <br/> |
   
## <a name="locating-the-appropriate-hidden-message-and-attachment"></a>查找相应的隐藏邮件和附件

现在, 我们知道 "收件箱" 的邮件下载历史记录位于隐藏邮件附件的 " **PidTagAttachDataBinary** " 属性中, 查找相应隐藏邮件的相应附件的过程将包含以下内容过程 
  
1. [查找相应的隐藏邮件](#OL15Con_AuxRef_LocatingMsgsUIDLHistory_FindHiddenMsg)
    
2. [查找隐藏邮件的相应附件](#OL15Con_AuxRef_LocatingMsgsUIDLHistory_FindAttachment)
    
3. [访问邮件附件的 PidTagAttachDataBinary 属性](#OL15Con_AuxRef_LocatingMsgsUIDLHistory_AccessProp)

<a name="OL15Con_AuxRef_LocatingMsgsUIDLHistory_FindHiddenMsg"> </a>

### <a name="find-the-appropriate-hidden-message"></a>查找相应的隐藏邮件

1. 在由**MUID_PROFILE_INSTANCE**指定的配置文件部分中, 获取配置文件中的[PidTagSearchKey](https://msdn.microsoft.com/library/fcab369a-a1f4-4425-a272-e35046914a4d%28Office.15%29.aspx) (**PR_SEARCH_KEY**) 属性。
    
2. 通过调用**IMAPIContainer:: GetContentsTable**打开 "收件箱" 文件夹的相关内容。
    
3. 创建基于[PidTagConversationKey](https://msdn.microsoft.com/library/52c97d6c-7f4b-4522-aeac-0c1ed8475952%28Office.15%29.aspx) (**PR_CONVERSATION_KEY**)、 **PidTagSearchKey** (**PR_SEARCH_KEY**) 和[PidTagMessageClass](https://msdn.microsoft.com/library/1e704023-1992-4b43-857e-0a7da7bc8e87%28Office.15%29.aspx) (**PR_MESSAGE_CLASS**) 属性的限制, 以获取一个表,包含收件箱的关联内容中的所有隐藏邮件。 下面是从[查找 POP3 UIDL 历史记录](https://blogs.msdn.com/b/stephen_griffin/archive/2012/12/03/locating-the-pop3-uidl-history.aspx)中提取的限制的示例。
    
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

4. 从该表中, 使用**IMAPITable:: FindRow**查找隐藏的邮件。
    
5. 如果步骤4未能找到隐藏的邮件, 请将该限制更改为使用**PidTagSearchKey** (**PR_SEARCH_KEY**) 而不是**PidTagConversationKey**, 如下所示:
    
   ```cpp
    rgRes[1].res.resProperty.ulPropTag = rgProps[0].ulPropTag = PR_SEARCH_KEY;
   ```

6. 使用**IMAPITable:: FindRow**查找隐藏的邮件。 
    
7. 如果步骤6失败, 请将限制更改为使用[PidTagSubject](https://msdn.microsoft.com/library/aa7ba4d9-c5e0-4ce7-a34e-65f675223bc9%28Office.15%29.aspx) (**PR_SUBJECT**) 等于以下值 (如下所示, 使用`printf`样式替代为简洁起见)。 
    
   ```cpp
    "Outlook Message Manager (%s) (KEY: %s)", PR_PROFILE_NAME, HexFromBin(PR_SEARCH_KEY)
   ```

8. 使用**IMAPITable:: FindRow**查找隐藏的邮件。
    
9. 如果运行的是 Outlook 2010 或更高版本, 请分别使用**PidTagProfileName** (**PR_PROFILE_NAME**) 和**PidTagSearchKey** (**PR_SEARCH_KEY**) 的以下值。
    
   ```cpp
    CHAR g_szGeneralKey[] = "General Key"; 
    const SBinary g_binGeneralKey = {sizeof(g_szGeneralKey), (LPBYTE)g_szGeneralKey};
   ```

   运行步骤3至8。 如果这样做未能找到邮件, 则回退到原始步骤3至8。
    
10. 打开在步骤4、6或8中找到的隐藏邮件。

<a name="OL15Con_AuxRef_LocatingMsgsUIDLHistory_FindAttachment"> </a>

### <a name="find-the-appropriate-attachment-of-the-hidden-message"></a>查找隐藏邮件的相应附件

由于隐藏的邮件可能包含多个附件, 因此请按以下顺序查找相应的附件。
  
> [!NOTE]
> 为简洁起见, 此`printf`过程再次使用样式替换。 

1. 查找其[PidTagAttachLongFilename](https://msdn.microsoft.com/library/83b69e8f-0b5a-4992-b5b8-160d3bdfa22a%28Office.15%29.aspx) (**PR_ATTACH_LONG_FILENAME**) 匹配以下字符串的附件, 其中`szEmailAddress`是用户配置文件中指定的用户的 SMTP 地址。 . 
    
   ```cpp
    "BlobPOP%s", szEmailAddress
   ```

2. 查找其[PidTagAttachFilename](https://msdn.microsoft.com/library/cbf34dd6-7733-47f6-9c41-9d82656ca9dc%28Office.15%29.aspx) (**PR_ATTACH_FILENAME**) 与 "BlobPOP% s" 匹配的附件`szEmailAddress`。
    
3. 查找其[PidTagDisplayName](https://msdn.microsoft.com/library/bd094e00-5c60-4bb3-9a45-b943fab52876%28Office.15%29.aspx) (**PR_DISPLAY_NAME**) 与 "BlobPOP% s" 匹配的附件`szEmailAddress`。
    
4. 查找其**PidTagAttachFilename** (**PR_ATTACH_FILENAME**) 与 "Blob% 8" 相匹配的附件`dwAcctUID`, 其中`dwAcctUID`来自[PROP_ACCT_MINI_UID](prop_acct_mini_uid.md)。 您可以使用[IOlkAccount:: GetProp](iolkaccount-getprop.md)方法访问**PROP_ACCT_MINI_UID**属性。 

<a name="OL15Con_AuxRef_LocatingMsgsUIDLHistory_AccessProp"> </a>

### <a name="access-the-pidtagattachdatabinary-property-of-the-message-attachment"></a>访问邮件附件的 PidTagAttachDataBinary 属性

找到隐藏邮件的相应邮件附件后, 请使用**IMAPIProp:: GetProps**读取附件的**PidTagAttachDataBinary**属性。 

<a name="OL15Con_AuxRef_LocatingMsgsUIDLHistory_NextSteps"> </a>

## <a name="next-steps"></a>后续步骤

您已从本主题中学到的内容如何查找 POP3 邮件客户端的收件箱的邮件下载历史记录。 请参阅[分析 POP3 帐户的邮件下载历史记录](parsing-the-message-download-history-for-a-pop3-account.md), 了解如何分析此历史记录以识别收件箱中已下载或已删除的邮件。 

<a name="OL15Con_AuxRef_LocatingMsgsUIDLHistory_AdditionalRsc"> </a>

## <a name="see-also"></a>另请参阅

- [管理 POP3 帐户的邮件下载](managing-message-downloads-for-pop3-accounts.md)   
- [分析 POP3 帐户的邮件下载历史记录](parsing-the-message-download-history-for-a-pop3-account.md)
- [查找 POP3 UIDL 历史记录](https://blogs.msdn.com/b/stephen_griffin/archive/2012/12/03/locating-the-pop3-uidl-history.aspx)
    

