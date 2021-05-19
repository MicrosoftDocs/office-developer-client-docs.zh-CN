---
title: Folder-Associated信息表
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: b72a0d36-c489-41d6-af57-72fbf4b7a3f5
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 2332c2a2f7eb46816eab5305b73344e25b2832d7
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33426413"
---
# <a name="folder-associated-information-tables"></a><span data-ttu-id="d60d3-103">Folder-Associated信息表</span><span class="sxs-lookup"><span data-stu-id="d60d3-103">Folder-Associated Information Tables</span></span>

  
  
<span data-ttu-id="d60d3-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d60d3-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="d60d3-105">MAPI 为处理MAPI_ASSOCIATED表时使用的各种 MAPI 组件定义 mapI 标志。</span><span class="sxs-lookup"><span data-stu-id="d60d3-105">MAPI defines the MAPI_ASSOCIATED flag for various MAPI components to use when dealing with associated information tables.</span></span> <span data-ttu-id="d60d3-106">邮件存储中的每个文件夹都应有一个关联的内容表及其标准内容表。</span><span class="sxs-lookup"><span data-stu-id="d60d3-106">Each folder in a message store should have an associated contents table along with its standard contents table.</span></span> <span data-ttu-id="d60d3-107">客户端应用程序将特殊邮件存储在文件夹的关联内容表中，以保存表单和视图。</span><span class="sxs-lookup"><span data-stu-id="d60d3-107">Client applications store special messages in a folder's associated contents table to hold forms and views.</span></span> <span data-ttu-id="d60d3-108">事实上，为了支持表单和视图，邮件存储提供程序必须实现关联的内容表。</span><span class="sxs-lookup"><span data-stu-id="d60d3-108">In fact, to support forms and views, your message store provider must implement associated contents tables.</span></span>
  
<span data-ttu-id="d60d3-109">若要实现关联的内容表，您的存储提供程序必须执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="d60d3-109">To implement associated contents tables, your store provider must do the following:</span></span>
  
- <span data-ttu-id="d60d3-110">支持 [IMAPIContainer：：GetContentsTable](imapicontainer-getcontentstable.md) 方法中的 MAPI_ASSOCIATED 标志，以便客户端应用程序可以获取文件夹的关联内容表，而不是标准内容表。</span><span class="sxs-lookup"><span data-stu-id="d60d3-110">Support the MAPI_ASSOCIATED flag in the [IMAPIContainer::GetContentsTable](imapicontainer-getcontentstable.md) method so client applications can get the folder's associated contents table instead of the standard contents table.</span></span> 
    
- <span data-ttu-id="d60d3-111">支持 [IMAPIFolder：：CreateMessage](imapifolder-createmessage.md) 方法中的 MAPI_ASSOCIATED 标志，以便客户端应用程序可以将消息添加到文件夹的关联内容表中。</span><span class="sxs-lookup"><span data-stu-id="d60d3-111">Support the MAPI_ASSOCIATED flag in the [IMAPIFolder::CreateMessage](imapifolder-createmessage.md) method so client applications can add messages to a folder's associated contents table.</span></span> 
    
- <span data-ttu-id="d60d3-112">在文件夹MAPI_ACCESS_CREATE_ASSOCIATED [PidTagAccess](pidtagaccess-canonical-property.md) PR_ACCESS (设置) 位。 </span><span class="sxs-lookup"><span data-stu-id="d60d3-112">Set the MAPI_ACCESS_CREATE_ASSOCIATED bit in the **PR_ACCESS** ([PidTagAccess](pidtagaccess-canonical-property.md)) property on folder objects.</span></span>
    
- <span data-ttu-id="d60d3-113">支持 [IMAPIFolder：：EmptyFolder](imapifolder-emptyfolder.md) 方法中的 DEL_ASSOCIATED 标记。</span><span class="sxs-lookup"><span data-stu-id="d60d3-113">Support the DEL_ASSOCIATED flag in the [IMAPIFolder::EmptyFolder](imapifolder-emptyfolder.md) method.</span></span> 
    
- <span data-ttu-id="d60d3-114">为MSGFLAG_ASSOCIATED内容表中的邮件设置 PR_MESSAGE_FLAGS  ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) 属性中的位。</span><span class="sxs-lookup"><span data-stu-id="d60d3-114">Set the MSGFLAG_ASSOCIATED bit in the **PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) property for messages in the associated contents table.</span></span>
    
- <span data-ttu-id="d60d3-115">公开并响应文件夹 **PR_FOLDER_ASSOCIATED_CONTENTS (** [PidTagFolderAssociatedContents](pidtagfolderassociatedcontents-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="d60d3-115">Expose and respond to the **PR_FOLDER_ASSOCIATED_CONTENTS** ([PidTagFolderAssociatedContents](pidtagfolderassociatedcontents-canonical-property.md)) property on folders.</span></span>
    
- <span data-ttu-id="d60d3-116">维护文件夹 **PR_ASSOC_CONTENT_COUNT (** [PidTagAssociatedContentCount](pidtagassociatedcontentcount-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="d60d3-116">Maintain the **PR_ASSOC_CONTENT_COUNT** ([PidTagAssociatedContentCount](pidtagassociatedcontentcount-canonical-property.md)) property on folders.</span></span>
    
<span data-ttu-id="d60d3-117">[PidTagStoreSupportMask PR_STORE_SUPPORT_MASK (PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md)) 属性中没有任何位可指示邮件存储提供程序是否支持关联的内容表。 </span><span class="sxs-lookup"><span data-stu-id="d60d3-117">There is no bit in the **PR_STORE_SUPPORT_MASK** ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md)) property to indicate whether your message store provider supports associated contents tables.</span></span> <span data-ttu-id="d60d3-118">如果邮件存储提供程序不支持这些方法，则当客户端应用程序MAPI_E_NO_SUPPORT上述任何具有 MAPI_ASSOCIATED 标志的方法时，应返回MAPI_ASSOCIATED消息。</span><span class="sxs-lookup"><span data-stu-id="d60d3-118">If your message store provider does not support them, it should return MAPI_E_NO_SUPPORT when client applications call any of the above methods with the MAPI_ASSOCIATED flag.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d60d3-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d60d3-119">See also</span></span>



[<span data-ttu-id="d60d3-120">邮件存储功能</span><span class="sxs-lookup"><span data-stu-id="d60d3-120">Message Store Features</span></span>](message-store-features.md)

