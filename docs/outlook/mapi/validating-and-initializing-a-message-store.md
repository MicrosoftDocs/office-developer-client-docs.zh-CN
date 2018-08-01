---
title: 验证和初始化邮件存储区
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 74f0a1fe-2a79-4b32-ab88-85a8839a2639
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 48883ec33db9ffd6b3e7cc6e16ae9c2487a31607
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779093"
---
# <a name="validating-and-initializing-a-message-store"></a><span data-ttu-id="53156-103">验证和初始化邮件存储区</span><span class="sxs-lookup"><span data-stu-id="53156-103">Validating and Initializing a Message Store</span></span>

  
  
<span data-ttu-id="53156-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="53156-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="53156-105">打开时的消息存储通过[IMAPISession::OpenMsgStore](imapisession-openmsgstore.md)方法而不设置 MDB_NO_MAIL 标志，MAPI 创建几个文件夹，并将其分配默认名称和角色。</span><span class="sxs-lookup"><span data-stu-id="53156-105">When you open a message store through the [IMAPISession::OpenMsgStore](imapisession-openmsgstore.md) method without setting the MDB_NO_MAIL flag, MAPI creates several folders and assigns them default names and roles.</span></span> <span data-ttu-id="53156-106">MAPI 负责创建这些文件夹，以避免将不可避免发生，如果客户端或消息存储提供程序负责创建不兼容性。</span><span class="sxs-lookup"><span data-stu-id="53156-106">MAPI is responsible for creating these folders to avoid the incompatibilities that would inevitably occur if either clients or message store providers were responsible for the creation.</span></span> 
  
<span data-ttu-id="53156-107">有时很有必要，若要验证已创建相应的文件夹和它们是有效。</span><span class="sxs-lookup"><span data-stu-id="53156-107">Sometimes it is necessary to verify that the appropriate folders have been created and that they are valid.</span></span> <span data-ttu-id="53156-108">[HrValidateIPMSubtree](hrvalidateipmsubtree.md)函数是可实现此目的。</span><span class="sxs-lookup"><span data-stu-id="53156-108">The [HrValidateIPMSubtree](hrvalidateipmsubtree.md) function is available for this purpose.</span></span> <span data-ttu-id="53156-109">如果您要验证默认的邮件存储，传递 MAPI_FULL_IPM_TREE 标志。</span><span class="sxs-lookup"><span data-stu-id="53156-109">If you are validating the default message store, pass the MAPI_FULL_IPM_TREE flag.</span></span> <span data-ttu-id="53156-110">为默认的邮件存储创建更复杂的一组文件夹。</span><span class="sxs-lookup"><span data-stu-id="53156-110">A more extensive group of folders is created for the default message store.</span></span> <span data-ttu-id="53156-111">当**HrValidateIPMSubtree**接收 MAPI_FULL_IPM_TREE 标志时，它会检查的以下文件夹：</span><span class="sxs-lookup"><span data-stu-id="53156-111">When **HrValidateIPMSubtree** receives the MAPI_FULL_IPM_TREE flag, it checks for the following folders:</span></span> 
  
- <span data-ttu-id="53156-112">IPM 子树的根文件夹</span><span class="sxs-lookup"><span data-stu-id="53156-112">Root folder for the IPM subtree</span></span>
    
- <span data-ttu-id="53156-113">IPM 根文件夹中的已删除的项目文件夹</span><span class="sxs-lookup"><span data-stu-id="53156-113">Deleted Items folder in the IPM root folder</span></span>
    
- <span data-ttu-id="53156-114">IPM 根文件夹中的收件箱文件夹</span><span class="sxs-lookup"><span data-stu-id="53156-114">Inbox folder in the IPM root folder</span></span>
    
- <span data-ttu-id="53156-115">发件箱文件夹中的 IPM 根文件夹</span><span class="sxs-lookup"><span data-stu-id="53156-115">Outbox folder in the IPM root folder</span></span>
    
- <span data-ttu-id="53156-116">发送项目文件夹 IPM 根文件夹中</span><span class="sxs-lookup"><span data-stu-id="53156-116">Sent Items folder in the IPM root folder</span></span>
    
- <span data-ttu-id="53156-117">消息存储的根文件夹中的文件夹视图</span><span class="sxs-lookup"><span data-stu-id="53156-117">Folder views in the message store's root folder</span></span>
    
- <span data-ttu-id="53156-118">消息存储的根文件夹中的公共视图</span><span class="sxs-lookup"><span data-stu-id="53156-118">Common views in the message store's root folder</span></span>
    
- <span data-ttu-id="53156-119">消息存储库的根文件夹中的搜索文件夹</span><span class="sxs-lookup"><span data-stu-id="53156-119">Search folder in the message store's root folder</span></span>
    
<span data-ttu-id="53156-120">如果消息存储不是默认值，您可以设置或不设置 MAPI_FULL_IPM_TREE 标志。</span><span class="sxs-lookup"><span data-stu-id="53156-120">If the message store is not the default, you can either set or not set the MAPI_FULL_IPM_TREE flag.</span></span> <span data-ttu-id="53156-121">时未设置此标志， **HrValidateIPMSubtree**检查的根文件夹将子树中，为已删除邮件文件夹中和消息的根文件夹将存储搜索结果。</span><span class="sxs-lookup"><span data-stu-id="53156-121">When this flag is not set, **HrValidateIPMSubtree** checks for only the root folder for the subtree, the Deleted Items folder, and the root folder for message store search results.</span></span> 
  
<span data-ttu-id="53156-122">若要初始化的消息存储，请在内存中存储以下属性以便它们随时可用：</span><span class="sxs-lookup"><span data-stu-id="53156-122">To initialize a message store, store the following properties in memory so that they are readily available:</span></span>
  
- <span data-ttu-id="53156-123">**PR_VALID_FOLDER_MASK**([PidTagValidFolderMask](pidtagvalidfoldermask-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="53156-123">**PR_VALID_FOLDER_MASK** ([PidTagValidFolderMask](pidtagvalidfoldermask-canonical-property.md))</span></span>
    
- <span data-ttu-id="53156-124">**PR_STORE_SUPPORT_MASK**([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="53156-124">**PR_STORE_SUPPORT_MASK** ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md))</span></span>
    
<span data-ttu-id="53156-125">这些属性是描述的邮件存储功能的位掩码。</span><span class="sxs-lookup"><span data-stu-id="53156-125">These properties are bitmasks that describe features of the message store.</span></span> <span data-ttu-id="53156-126">**PR_VALID_FOLDER_MASK**有一位设置为每个邮件存储区中存在具有有效的分配的项标识符的特殊文件夹。</span><span class="sxs-lookup"><span data-stu-id="53156-126">**PR_VALID_FOLDER_MASK** has one bit set for every special folder that exists in the message store and has an assigned entry identifier that is valid.</span></span> <span data-ttu-id="53156-127">有关访问这些文件夹和它们的项标识符的详细信息，请参阅[打开邮件存储文件夹](opening-a-message-store-folder.md)。</span><span class="sxs-lookup"><span data-stu-id="53156-127">For more information about accessing these folders and their entry identifiers, see [Opening a Message Store Folder](opening-a-message-store-folder.md).</span></span> 
  
 <span data-ttu-id="53156-128">**PR_STORE_SUPPORT_MASK**有一位设置为消息存储库中支持每个功能。</span><span class="sxs-lookup"><span data-stu-id="53156-128">**PR_STORE_SUPPORT_MASK** has one bit set for every feature supported in the message store.</span></span> <span data-ttu-id="53156-129">例如，如果的消息存储支持通知和带格式的文本，其**PR_STORE_SUPPORT_MASK**将具有 STORE_NOTIFY_OK 和 STORE_RTF_OK 设置了位。</span><span class="sxs-lookup"><span data-stu-id="53156-129">For example, if a message store supports notification and formatted text, its **PR_STORE_SUPPORT_MASK** will have the STORE_NOTIFY_OK and STORE_RTF_OK bits set.</span></span> 
  
<span data-ttu-id="53156-130">应存储在本地其他属性包括**PR_VALID_FOLDER_MASK**属性描述为有效的文件夹的项标识符。</span><span class="sxs-lookup"><span data-stu-id="53156-130">Other properties that should be stored locally include the entry identifiers for the folders that the **PR_VALID_FOLDER_MASK** property describes as valid.</span></span> <span data-ttu-id="53156-131">每个这些特殊文件夹，除收件箱文件夹中，有与之关联的项标识符属性。</span><span class="sxs-lookup"><span data-stu-id="53156-131">Each of these special folders, except for the Inbox folder, has an entry identifier property associated with it.</span></span> <span data-ttu-id="53156-132">例如，发件箱文件夹的条目标识符是其**PR_IPM_OUTBOX_ENTRYID** ([PidTagIpmOutboxEntryId](pidtagipmoutboxentryid-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="53156-132">For example, the entry identifier for the Outbox folder is its **PR_IPM_OUTBOX_ENTRYID** ([PidTagIpmOutboxEntryId](pidtagipmoutboxentryid-canonical-property.md)) property.</span></span> <span data-ttu-id="53156-133">由于这些文件夹是将经常打开的文件夹，最好具有其随时可用的项标识符。</span><span class="sxs-lookup"><span data-stu-id="53156-133">Because these folders are the folders that will be opened frequently, it is a good idea to have their entry identifiers readily available.</span></span>
  

