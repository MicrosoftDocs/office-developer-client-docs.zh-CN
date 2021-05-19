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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33433687"
---
# <a name="validating-and-initializing-a-message-store"></a><span data-ttu-id="a46db-103">验证和初始化邮件存储</span><span class="sxs-lookup"><span data-stu-id="a46db-103">Validating and Initializing a Message Store</span></span>

  
  
<span data-ttu-id="a46db-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="a46db-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="a46db-105">通过 [IMAPISession：：OpenMsgStore](imapisession-openmsgstore.md) 方法打开邮件存储而不设置 MDB_NO_MAIL 标志时，MAPI 将创建多个文件夹，并为其分配默认名称和角色。</span><span class="sxs-lookup"><span data-stu-id="a46db-105">When you open a message store through the [IMAPISession::OpenMsgStore](imapisession-openmsgstore.md) method without setting the MDB_NO_MAIL flag, MAPI creates several folders and assigns them default names and roles.</span></span> <span data-ttu-id="a46db-106">MAPI 负责创建这些文件夹，以避免在客户端或邮件存储提供程序负责创建时出现不必要的不兼容情况。</span><span class="sxs-lookup"><span data-stu-id="a46db-106">MAPI is responsible for creating these folders to avoid the incompatibilities that would inevitably occur if either clients or message store providers were responsible for the creation.</span></span> 
  
<span data-ttu-id="a46db-107">有时需要验证是否创建了适当的文件夹，并且这些文件夹是否有效。</span><span class="sxs-lookup"><span data-stu-id="a46db-107">Sometimes it is necessary to verify that the appropriate folders have been created and that they are valid.</span></span> <span data-ttu-id="a46db-108">[HrValidateIPMSubtree](hrvalidateipmsubtree.md)函数可用于此目的。</span><span class="sxs-lookup"><span data-stu-id="a46db-108">The [HrValidateIPMSubtree](hrvalidateipmsubtree.md) function is available for this purpose.</span></span> <span data-ttu-id="a46db-109">如果要验证默认邮件存储，请传递 MAPI_FULL_IPM_TREE 标志。</span><span class="sxs-lookup"><span data-stu-id="a46db-109">If you are validating the default message store, pass the MAPI_FULL_IPM_TREE flag.</span></span> <span data-ttu-id="a46db-110">为默认邮件存储创建了一组更广泛的文件夹。</span><span class="sxs-lookup"><span data-stu-id="a46db-110">A more extensive group of folders is created for the default message store.</span></span> <span data-ttu-id="a46db-111">当 **HrValidateIPMSubtree** 收到 MAPI_FULL_IPM_TREE 标志时，它将检查以下文件夹：</span><span class="sxs-lookup"><span data-stu-id="a46db-111">When **HrValidateIPMSubtree** receives the MAPI_FULL_IPM_TREE flag, it checks for the following folders:</span></span> 
  
- <span data-ttu-id="a46db-112">IPM 子树的根文件夹</span><span class="sxs-lookup"><span data-stu-id="a46db-112">Root folder for the IPM subtree</span></span>
    
- <span data-ttu-id="a46db-113">IPM 根文件夹中的"已删除邮件"文件夹</span><span class="sxs-lookup"><span data-stu-id="a46db-113">Deleted Items folder in the IPM root folder</span></span>
    
- <span data-ttu-id="a46db-114">IPM 根文件夹中的收件箱文件夹</span><span class="sxs-lookup"><span data-stu-id="a46db-114">Inbox folder in the IPM root folder</span></span>
    
- <span data-ttu-id="a46db-115">IPM 根文件夹中的发件箱文件夹</span><span class="sxs-lookup"><span data-stu-id="a46db-115">Outbox folder in the IPM root folder</span></span>
    
- <span data-ttu-id="a46db-116">IPM 根文件夹中的"已发送项目"文件夹</span><span class="sxs-lookup"><span data-stu-id="a46db-116">Sent Items folder in the IPM root folder</span></span>
    
- <span data-ttu-id="a46db-117">邮件存储的根文件夹中的文件夹视图</span><span class="sxs-lookup"><span data-stu-id="a46db-117">Folder views in the message store's root folder</span></span>
    
- <span data-ttu-id="a46db-118">邮件存储的根文件夹中的常见视图</span><span class="sxs-lookup"><span data-stu-id="a46db-118">Common views in the message store's root folder</span></span>
    
- <span data-ttu-id="a46db-119">邮件存储的根文件夹中的搜索文件夹</span><span class="sxs-lookup"><span data-stu-id="a46db-119">Search folder in the message store's root folder</span></span>
    
<span data-ttu-id="a46db-120">如果邮件存储不是默认存储，您可以设置或不设置MAPI_FULL_IPM_TREE标记。</span><span class="sxs-lookup"><span data-stu-id="a46db-120">If the message store is not the default, you can either set or not set the MAPI_FULL_IPM_TREE flag.</span></span> <span data-ttu-id="a46db-121">未设置此标志时 **，HrValidateIPMSubtree** 仅检查子树的根文件夹、"已删除邮件"文件夹以及邮件存储搜索结果的根文件夹。</span><span class="sxs-lookup"><span data-stu-id="a46db-121">When this flag is not set, **HrValidateIPMSubtree** checks for only the root folder for the subtree, the Deleted Items folder, and the root folder for message store search results.</span></span> 
  
<span data-ttu-id="a46db-122">若要初始化邮件存储，可在内存中存储以下属性，以便它们随时可用：</span><span class="sxs-lookup"><span data-stu-id="a46db-122">To initialize a message store, store the following properties in memory so that they are readily available:</span></span>
  
- <span data-ttu-id="a46db-123">**PR_VALID_FOLDER_MASK (** [PidTagValidFolderMask)](pidtagvalidfoldermask-canonical-property.md)</span><span class="sxs-lookup"><span data-stu-id="a46db-123">**PR_VALID_FOLDER_MASK** ([PidTagValidFolderMask](pidtagvalidfoldermask-canonical-property.md))</span></span>
    
- <span data-ttu-id="a46db-124">**PR_STORE_SUPPORT_MASK (** [PidTagStoreSupportMask)](pidtagstoresupportmask-canonical-property.md)</span><span class="sxs-lookup"><span data-stu-id="a46db-124">**PR_STORE_SUPPORT_MASK** ([PidTagStoreSupportMask](pidtagstoresupportmask-canonical-property.md))</span></span>
    
<span data-ttu-id="a46db-125">这些属性是描述邮件存储功能的位掩码。</span><span class="sxs-lookup"><span data-stu-id="a46db-125">These properties are bitmasks that describe features of the message store.</span></span> <span data-ttu-id="a46db-126">**PR_VALID_FOLDER_MASK** 邮件存储中每个特殊文件夹都有一个位集，并且分配有有效的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="a46db-126">**PR_VALID_FOLDER_MASK** has one bit set for every special folder that exists in the message store and has an assigned entry identifier that is valid.</span></span> <span data-ttu-id="a46db-127">有关访问这些文件夹及其条目标识符的信息，请参阅打开 [邮件存储文件夹](opening-a-message-store-folder.md)。</span><span class="sxs-lookup"><span data-stu-id="a46db-127">For more information about accessing these folders and their entry identifiers, see [Opening a Message Store Folder](opening-a-message-store-folder.md).</span></span> 
  
 <span data-ttu-id="a46db-128">**PR_STORE_SUPPORT_MASK** 邮件存储中支持的每一个功能都有一个位集。</span><span class="sxs-lookup"><span data-stu-id="a46db-128">**PR_STORE_SUPPORT_MASK** has one bit set for every feature supported in the message store.</span></span> <span data-ttu-id="a46db-129">例如，如果邮件存储支持通知和格式化文本，则其PR_STORE_SUPPORT_MASK将设置 STORE_NOTIFY_OK 和 STORE_RTF_OK 位。</span><span class="sxs-lookup"><span data-stu-id="a46db-129">For example, if a message store supports notification and formatted text, its **PR_STORE_SUPPORT_MASK** will have the STORE_NOTIFY_OK and STORE_RTF_OK bits set.</span></span> 
  
<span data-ttu-id="a46db-130">应本地存储的其他属性包括文件夹的条目标识符，PR_VALID_FOLDER_MASK **属性描述** 为有效的文件夹。</span><span class="sxs-lookup"><span data-stu-id="a46db-130">Other properties that should be stored locally include the entry identifiers for the folders that the **PR_VALID_FOLDER_MASK** property describes as valid.</span></span> <span data-ttu-id="a46db-131">除"收件箱"文件夹外，每个特殊文件夹都有一个与之关联的条目标识符属性。</span><span class="sxs-lookup"><span data-stu-id="a46db-131">Each of these special folders, except for the Inbox folder, has an entry identifier property associated with it.</span></span> <span data-ttu-id="a46db-132">例如，发件箱文件夹的条目标识符PR_IPM_OUTBOX_ENTRYID ([PidTagIpmOutboxEntryId](pidtagipmoutboxentryid-canonical-property.md)) 属性。 </span><span class="sxs-lookup"><span data-stu-id="a46db-132">For example, the entry identifier for the Outbox folder is its **PR_IPM_OUTBOX_ENTRYID** ([PidTagIpmOutboxEntryId](pidtagipmoutboxentryid-canonical-property.md)) property.</span></span> <span data-ttu-id="a46db-133">由于这些文件夹是经常打开的文件夹，因此建议让条目标识符随时可用。</span><span class="sxs-lookup"><span data-stu-id="a46db-133">Because these folders are the folders that will be opened frequently, it is a good idea to have their entry identifiers readily available.</span></span>
  

