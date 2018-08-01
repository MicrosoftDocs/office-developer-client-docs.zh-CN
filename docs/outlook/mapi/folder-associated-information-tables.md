---
title: 文件夹关联的信息表
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: b72a0d36-c489-41d6-af57-72fbf4b7a3f5
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 09cac591aac9d266571348531e378974b86a3a9d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774957"
---
# <a name="folder-associated-information-tables"></a><span data-ttu-id="23f7a-103">文件夹关联的信息表</span><span class="sxs-lookup"><span data-stu-id="23f7a-103">Folder-Associated Information Tables</span></span>

  
  
<span data-ttu-id="23f7a-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="23f7a-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="23f7a-105">MAPI 定义各种 MAPI 组件处理相关的信息表时要使用 MAPI_ASSOCIATED 标志。</span><span class="sxs-lookup"><span data-stu-id="23f7a-105">MAPI defines the MAPI_ASSOCIATED flag for various MAPI components to use when dealing with associated information tables.</span></span> <span data-ttu-id="23f7a-106">每个文件夹中的消息存储应有以及其标准内容表关联的内容表。</span><span class="sxs-lookup"><span data-stu-id="23f7a-106">Each folder in a message store should have an associated contents table along with its standard contents table.</span></span> <span data-ttu-id="23f7a-107">客户端应用程序的文件夹关联的内容表来保存表单和视图中存储特殊的邮件。</span><span class="sxs-lookup"><span data-stu-id="23f7a-107">Client applications store special messages in a folder's associated contents table to hold forms and views.</span></span> <span data-ttu-id="23f7a-108">实际上，若要支持表单和视图，消息存储提供程序必须实现关联的内容表。</span><span class="sxs-lookup"><span data-stu-id="23f7a-108">In fact, to support forms and views, your message store provider must implement associated contents tables.</span></span>
  
<span data-ttu-id="23f7a-109">若要实现关联的内容表，存储提供程序必须执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="23f7a-109">To implement associated contents tables, your store provider must do the following:</span></span>
  
- <span data-ttu-id="23f7a-110">支持 MAPI_ASSOCIATED 标志[IMAPIContainer::GetContentsTable](imapicontainer-getcontentstable.md)方法中，因此客户端应用程序可以获取文件夹的关联的内容而不是标准内容表的表。</span><span class="sxs-lookup"><span data-stu-id="23f7a-110">Support the MAPI_ASSOCIATED flag in the [IMAPIContainer::GetContentsTable](imapicontainer-getcontentstable.md) method so client applications can get the folder's associated contents table instead of the standard contents table.</span></span> 
    
- <span data-ttu-id="23f7a-111">支持 MAPI_ASSOCIATED 标志[IMAPIFolder::CreateMessage](imapifolder-createmessage.md)方法中，因此客户端应用程序可以将消息添加到的文件夹关联的内容表。</span><span class="sxs-lookup"><span data-stu-id="23f7a-111">Support the MAPI_ASSOCIATED flag in the [IMAPIFolder::CreateMessage](imapifolder-createmessage.md) method so client applications can add messages to a folder's associated contents table.</span></span> 
    
- <span data-ttu-id="23f7a-112">对文件夹对象的**PR_ACCESS** ([PidTagAccess](pidtagaccess-canonical-property.md)) 属性中设置 MAPI_ACCESS_CREATE_ASSOCIATED 位。</span><span class="sxs-lookup"><span data-stu-id="23f7a-112">Set the MAPI_ACCESS_CREATE_ASSOCIATED bit in the **PR_ACCESS** ([PidTagAccess](pidtagaccess-canonical-property.md)) property on folder objects.</span></span>
    
- <span data-ttu-id="23f7a-113">在[IMAPIFolder::EmptyFolder](imapifolder-emptyfolder.md)方法支持 DEL_ASSOCIATED 标志。</span><span class="sxs-lookup"><span data-stu-id="23f7a-113">Support the DEL_ASSOCIATED flag in the [IMAPIFolder::EmptyFolder](imapifolder-emptyfolder.md) method.</span></span> 
    
- <span data-ttu-id="23f7a-114">设置中的关联的内容表中的邮件的**PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) 属性位 MSGFLAG_ASSOCIATED。</span><span class="sxs-lookup"><span data-stu-id="23f7a-114">Set the MSGFLAG_ASSOCIATED bit in the **PR_MESSAGE_FLAGS** ([PidTagMessageFlags](pidtagmessageflags-canonical-property.md)) property for messages in the associated contents table.</span></span>
    
- <span data-ttu-id="23f7a-115">公开和响应对文件夹的**PR_FOLDER_ASSOCIATED_CONTENTS** ([PidTagFolderAssociatedContents](pidtagfolderassociatedcontents-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="23f7a-115">Expose and respond to the **PR_FOLDER_ASSOCIATED_CONTENTS** ([PidTagFolderAssociatedContents](pidtagfolderassociatedcontents-canonical-property.md)) property on folders.</span></span>
    
- <span data-ttu-id="23f7a-116">维护文件夹的**PR_ASSOC_CONTENT_COUNT** ([PidTagAssociatedContentCount](pidtagassociatedcontentcount-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="23f7a-116">Maintain the **PR_ASSOC_CONTENT_COUNT** ([PidTagAssociatedContentCount](pidtagassociatedcontentcount-canonical-property.md)) property on folders.</span></span>
    
<span data-ttu-id="23f7a-117">**PR_STORE_SUPPORT_MASK** ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md)) 属性，以指示消息存储提供程序是否支持关联的内容表中没有任何位。</span><span class="sxs-lookup"><span data-stu-id="23f7a-117">There is no bit in the **PR_STORE_SUPPORT_MASK** ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md)) property to indicate whether your message store provider supports associated contents tables.</span></span> <span data-ttu-id="23f7a-118">如果消息存储提供程序不支持它们，则应在客户端应用程序调用任何 MAPI_ASSOCIATED 标志与上述方法时返回 MAPI_E_NO_SUPPORT。</span><span class="sxs-lookup"><span data-stu-id="23f7a-118">If your message store provider does not support them, it should return MAPI_E_NO_SUPPORT when client applications call any of the above methods with the MAPI_ASSOCIATED flag.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="23f7a-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="23f7a-119">See also</span></span>



[<span data-ttu-id="23f7a-120">邮件存储区功能</span><span class="sxs-lookup"><span data-stu-id="23f7a-120">Message Store Features</span></span>](message-store-features.md)

