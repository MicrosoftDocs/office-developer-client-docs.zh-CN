---
title: 验证和初始化邮件存储
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 74f0a1fe-2a79-4b32-ab88-85a8839a2639
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 77b3f707fc36a868de5acd7c7ba4642a1da4e3c9
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32329580"
---
# <a name="validating-and-initializing-a-message-store"></a><span data-ttu-id="683cb-103">验证和初始化邮件存储</span><span class="sxs-lookup"><span data-stu-id="683cb-103">Validating and Initializing a Message Store</span></span>

  
  
<span data-ttu-id="683cb-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="683cb-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="683cb-105">通过[IMAPISession:: OpenMsgStore](imapisession-openmsgstore.md)方法打开邮件库时, 如果不设置 MDB_NO_MAIL 标志, MAPI 会创建多个文件夹并为其分配默认名称和角色。</span><span class="sxs-lookup"><span data-stu-id="683cb-105">When you open a message store through the [IMAPISession::OpenMsgStore](imapisession-openmsgstore.md) method without setting the MDB_NO_MAIL flag, MAPI creates several folders and assigns them default names and roles.</span></span> <span data-ttu-id="683cb-106">MAPI 负责创建这些文件夹, 以避免在客户端或邮件存储提供程序负责创建时不可避免的不兼容情况。</span><span class="sxs-lookup"><span data-stu-id="683cb-106">MAPI is responsible for creating these folders to avoid the incompatibilities that would inevitably occur if either clients or message store providers were responsible for the creation.</span></span> 
  
<span data-ttu-id="683cb-107">有时, 有必要验证是否已创建了适当的文件夹以及它们是否有效。</span><span class="sxs-lookup"><span data-stu-id="683cb-107">Sometimes it is necessary to verify that the appropriate folders have been created and that they are valid.</span></span> <span data-ttu-id="683cb-108">[HrValidateIPMSubtree](hrvalidateipmsubtree.md)函数可用于此目的。</span><span class="sxs-lookup"><span data-stu-id="683cb-108">The [HrValidateIPMSubtree](hrvalidateipmsubtree.md) function is available for this purpose.</span></span> <span data-ttu-id="683cb-109">如果要验证默认邮件存储, 请传递 MAPI_FULL_IPM_TREE 标志。</span><span class="sxs-lookup"><span data-stu-id="683cb-109">If you are validating the default message store, pass the MAPI_FULL_IPM_TREE flag.</span></span> <span data-ttu-id="683cb-110">为默认邮件存储区创建更广泛的文件夹组。</span><span class="sxs-lookup"><span data-stu-id="683cb-110">A more extensive group of folders is created for the default message store.</span></span> <span data-ttu-id="683cb-111">当**HrValidateIPMSubtree**收到 MAPI_FULL_IPM_TREE 标志时, 它会检查以下文件夹:</span><span class="sxs-lookup"><span data-stu-id="683cb-111">When **HrValidateIPMSubtree** receives the MAPI_FULL_IPM_TREE flag, it checks for the following folders:</span></span> 
  
- <span data-ttu-id="683cb-112">IPM 子树的根文件夹</span><span class="sxs-lookup"><span data-stu-id="683cb-112">Root folder for the IPM subtree</span></span>
    
- <span data-ttu-id="683cb-113">IPM 根文件夹中的 "已删除邮件" 文件夹</span><span class="sxs-lookup"><span data-stu-id="683cb-113">Deleted Items folder in the IPM root folder</span></span>
    
- <span data-ttu-id="683cb-114">IPM 根文件夹中的 "收件箱" 文件夹</span><span class="sxs-lookup"><span data-stu-id="683cb-114">Inbox folder in the IPM root folder</span></span>
    
- <span data-ttu-id="683cb-115">IPM 根文件夹中的 "发件箱" 文件夹</span><span class="sxs-lookup"><span data-stu-id="683cb-115">Outbox folder in the IPM root folder</span></span>
    
- <span data-ttu-id="683cb-116">IPM 根文件夹中的 "已发送邮件" 文件夹</span><span class="sxs-lookup"><span data-stu-id="683cb-116">Sent Items folder in the IPM root folder</span></span>
    
- <span data-ttu-id="683cb-117">邮件存储区的根文件夹中的文件夹视图</span><span class="sxs-lookup"><span data-stu-id="683cb-117">Folder views in the message store's root folder</span></span>
    
- <span data-ttu-id="683cb-118">邮件存储区的根文件夹中的常见视图</span><span class="sxs-lookup"><span data-stu-id="683cb-118">Common views in the message store's root folder</span></span>
    
- <span data-ttu-id="683cb-119">邮件存储区的根文件夹中的 "搜索文件夹"</span><span class="sxs-lookup"><span data-stu-id="683cb-119">Search folder in the message store's root folder</span></span>
    
<span data-ttu-id="683cb-120">如果邮件存储不是默认的, 则可以设置或不设置 MAPI_FULL_IPM_TREE 标志。</span><span class="sxs-lookup"><span data-stu-id="683cb-120">If the message store is not the default, you can either set or not set the MAPI_FULL_IPM_TREE flag.</span></span> <span data-ttu-id="683cb-121">如果未设置此标志, 则**HrValidateIPMSubtree**仅检查子树的根文件夹、"已删除邮件" 文件夹和邮件存储区搜索结果的根文件夹。</span><span class="sxs-lookup"><span data-stu-id="683cb-121">When this flag is not set, **HrValidateIPMSubtree** checks for only the root folder for the subtree, the Deleted Items folder, and the root folder for message store search results.</span></span> 
  
<span data-ttu-id="683cb-122">若要初始化邮件存储区, 请将以下属性存储在内存中, 以供随时使用:</span><span class="sxs-lookup"><span data-stu-id="683cb-122">To initialize a message store, store the following properties in memory so that they are readily available:</span></span>
  
- <span data-ttu-id="683cb-123">**PR_VALID_FOLDER_MASK**([PidTagValidFolderMask](pidtagvalidfoldermask-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="683cb-123">**PR_VALID_FOLDER_MASK** ([PidTagValidFolderMask](pidtagvalidfoldermask-canonical-property.md))</span></span>
    
- <span data-ttu-id="683cb-124">**PR_STORE_SUPPORT_MASK**([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="683cb-124">**PR_STORE_SUPPORT_MASK** ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md))</span></span>
    
<span data-ttu-id="683cb-125">这些属性是用于描述邮件存储的功能的位掩码。</span><span class="sxs-lookup"><span data-stu-id="683cb-125">These properties are bitmasks that describe features of the message store.</span></span> <span data-ttu-id="683cb-126">对于邮件存储区中存在的每个特殊文件夹, **PR_VALID_FOLDER_MASK**都设置了一个位, 并且具有有效的已分配条目标识符。</span><span class="sxs-lookup"><span data-stu-id="683cb-126">**PR_VALID_FOLDER_MASK** has one bit set for every special folder that exists in the message store and has an assigned entry identifier that is valid.</span></span> <span data-ttu-id="683cb-127">有关访问这些文件夹及其条目标识符的详细信息, 请参阅[打开邮件存储文件夹](opening-a-message-store-folder.md)。</span><span class="sxs-lookup"><span data-stu-id="683cb-127">For more information about accessing these folders and their entry identifiers, see [Opening a Message Store Folder](opening-a-message-store-folder.md).</span></span> 
  
 <span data-ttu-id="683cb-128">**PR_STORE_SUPPORT_MASK**为邮件存储区中支持的每项功能设置了一个位。</span><span class="sxs-lookup"><span data-stu-id="683cb-128">**PR_STORE_SUPPORT_MASK** has one bit set for every feature supported in the message store.</span></span> <span data-ttu-id="683cb-129">例如, 如果邮件存储区支持通知和格式化文本, 则其**PR_STORE_SUPPORT_MASK**将设置 STORE_NOTIFY_OK 和 STORE_RTF_OK 位。</span><span class="sxs-lookup"><span data-stu-id="683cb-129">For example, if a message store supports notification and formatted text, its **PR_STORE_SUPPORT_MASK** will have the STORE_NOTIFY_OK and STORE_RTF_OK bits set.</span></span> 
  
<span data-ttu-id="683cb-130">应在本地存储的其他属性包括**PR_VALID_FOLDER_MASK**属性描述为有效的文件夹的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="683cb-130">Other properties that should be stored locally include the entry identifiers for the folders that the **PR_VALID_FOLDER_MASK** property describes as valid.</span></span> <span data-ttu-id="683cb-131">每个特殊文件夹 ("收件箱" 文件夹除外) 都有一个与之关联的条目标识符属性。</span><span class="sxs-lookup"><span data-stu-id="683cb-131">Each of these special folders, except for the Inbox folder, has an entry identifier property associated with it.</span></span> <span data-ttu-id="683cb-132">例如, "发件箱" 文件夹的条目标识符是其**PR_IPM_OUTBOX_ENTRYID** ([PidTagIpmOutboxEntryId](pidtagipmoutboxentryid-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="683cb-132">For example, the entry identifier for the Outbox folder is its **PR_IPM_OUTBOX_ENTRYID** ([PidTagIpmOutboxEntryId](pidtagipmoutboxentryid-canonical-property.md)) property.</span></span> <span data-ttu-id="683cb-133">由于这些文件夹是将频繁打开的文件夹, 因此最好让其条目标识符易于使用。</span><span class="sxs-lookup"><span data-stu-id="683cb-133">Because these folders are the folders that will be opened frequently, it is a good idea to have their entry identifiers readily available.</span></span>
  

