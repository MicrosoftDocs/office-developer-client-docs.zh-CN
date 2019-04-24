---
title: 层次结构表
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: b8aa6b36-d6e5-4e1f-8ac5-5d6a78a70bf8
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 2a1461f0c7196cd425d9736f5837b742bedd4fb5
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32344571"
---
# <a name="hierarchy-tables"></a><span data-ttu-id="9683c-103">层次结构表</span><span class="sxs-lookup"><span data-stu-id="9683c-103">Hierarchy Tables</span></span>

  
  
<span data-ttu-id="9683c-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="9683c-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="9683c-105">层次结构表包含有关邮件存储区中的文件夹或通讯簿容器中的容器的信息。</span><span class="sxs-lookup"><span data-stu-id="9683c-105">A hierarchy table contains information about the folders in a message store or the containers in an address book container.</span></span> <span data-ttu-id="9683c-106">层次结构表中的每一行都包含一组列, 其中包含一个文件夹或通讯簿容器的相关信息。</span><span class="sxs-lookup"><span data-stu-id="9683c-106">Each row of a hierarchy table contains a set of columns with information about one folder or address book container.</span></span> <span data-ttu-id="9683c-107">层次结构表主要由客户端使用, 并由邮件存储提供程序实现, 以显示文件夹和子文件夹树, 并由通讯簿提供程序实现, 以显示通讯簿中的容器树。</span><span class="sxs-lookup"><span data-stu-id="9683c-107">Hierarchy tables are primarily used by clients and implemented by message store providers to show a tree of folders and subfolders and implemented by address book providers to show a tree of containers in the address book.</span></span> <span data-ttu-id="9683c-108">无法保留子容器的容器 (由其**PR_CONTAINER_FLAGS** ([PidTagContainerFlags](pidtagcontainerflags-canonical-property.md)) 属性中缺少 AB_SUBCONTAINERS 标志表示) 不实现层次结构表。</span><span class="sxs-lookup"><span data-stu-id="9683c-108">Containers that cannot hold subcontainers, as indicated by the absence of the AB_SUBCONTAINERS flag in their **PR_CONTAINER_FLAGS** ([PidTagContainerFlags](pidtagcontainerflags-canonical-property.md)) property, do not implement a hierarchy table.</span></span>
  
<span data-ttu-id="9683c-109">可通过调用来访问层次结构表:</span><span class="sxs-lookup"><span data-stu-id="9683c-109">A hierarchy table can be accessed by calling:</span></span>
  
- <span data-ttu-id="9683c-110">[IMAPIContainer:: GetHierarchyTable](imapicontainer-gethierarchytable.md)。</span><span class="sxs-lookup"><span data-stu-id="9683c-110">[IMAPIContainer::GetHierarchyTable](imapicontainer-gethierarchytable.md).</span></span>
    
    - <span data-ttu-id="9683c-111">和</span><span class="sxs-lookup"><span data-stu-id="9683c-111">Or -</span></span>
    
- <span data-ttu-id="9683c-112">[IMAPIProp:: OpenProperty](imapiprop-openproperty.md)将**PR_CONTAINER_HIERARCHY** ([PidTagContainerHierarchy](pidtagcontainerhierarchy-canonical-property.md)) 作为属性标记, 将 IID_IMAPITable 作为接口标识符进行传递。</span><span class="sxs-lookup"><span data-stu-id="9683c-112">[IMAPIProp::OpenProperty](imapiprop-openproperty.md) passing **PR_CONTAINER_HIERARCHY** ([PidTagContainerHierarchy](pidtagcontainerhierarchy-canonical-property.md)) as the property tag and IID_IMAPITable as the interface identifier.</span></span>
    
<span data-ttu-id="9683c-113">容器和文件夹必须支持这两种方法来检索表属性。</span><span class="sxs-lookup"><span data-stu-id="9683c-113">Containers and folders must support both techniques for retrieving table properties.</span></span> <span data-ttu-id="9683c-114">服务提供商仅支持一种访问这些表的方式是不可接受的, 因为客户端希望能够做出选择。</span><span class="sxs-lookup"><span data-stu-id="9683c-114">It is unacceptable for service providers to support only one way to access these tables because clients expect to have the choice.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="9683c-115">不能保证存储提供程序遵循为层次结构表指定的排序顺序集。</span><span class="sxs-lookup"><span data-stu-id="9683c-115">Store providers are not guaranteed to honor the sort order set specified for hierarchy tables.</span></span> 
  
<span data-ttu-id="9683c-116">对**IMAPIProp:: OpenProperty**的调用需要通过打开其对应的属性**PR_CONTAINER_HIERARCHY**来访问层次结构表。</span><span class="sxs-lookup"><span data-stu-id="9683c-116">The call to **IMAPIProp::OpenProperty** involves accessing the hierarchy table by opening its corresponding property, **PR_CONTAINER_HIERARCHY**.</span></span> <span data-ttu-id="9683c-117">[! 注意] 尽管无法通过文件夹或容器的[IMAPIProp:: GetProps](imapiprop-getprops.md)方法检索**PR_CONTAINER_HIERARCHY** , 但它包含在由[IMAPIProp:: GetPropList](imapiprop-getproplist.md)方法返回的属性标记数组中。</span><span class="sxs-lookup"><span data-stu-id="9683c-117">Although **PR_CONTAINER_HIERARCHY** cannot be retrieved through a folder or container's [IMAPIProp::GetProps](imapiprop-getprops.md) method, it is included in the property tag array that is returned by the [IMAPIProp::GetPropList](imapiprop-getproplist.md) method.</span></span> 
  
 <span data-ttu-id="9683c-118">**PR_CONTAINER_HIERARCHY**还可用于包含或排除复制操作中的层次结构表。</span><span class="sxs-lookup"><span data-stu-id="9683c-118">**PR_CONTAINER_HIERARCHY** can also be used to include or exclude a hierarchy table from a copy operation.</span></span> <span data-ttu-id="9683c-119">如果客户端在*lpExcludeProps*参数中为[IMAPIProp:: CopyTo](imapiprop-copyto.md)在复制操作中指定了**PR_CONTAINER_HIERARCHY** , 则新的文件夹或容器将不支持原始文件夹或容器的层次结构表。</span><span class="sxs-lookup"><span data-stu-id="9683c-119">If a client specifies **PR_CONTAINER_HIERARCHY** in the  *lpExcludeProps*  parameter for [IMAPIProp::CopyTo](imapiprop-copyto.md) in a copy operation, the new folder or container will not support the hierarchy table of the original folder or container.</span></span> 
  
<span data-ttu-id="9683c-120">以下属性构成了层次结构表中所需的列集:</span><span class="sxs-lookup"><span data-stu-id="9683c-120">The following properties make up the required column set in a hierarchy table:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="9683c-121">**PR_COMMENT**([PidTagComment](pidtagcomment-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="9683c-121">**PR_COMMENT** ([PidTagComment](pidtagcomment-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="9683c-122">**PR_DEPTH**([PidTagDepth](pidtagdepth-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="9683c-122">**PR_DEPTH** ([PidTagDepth](pidtagdepth-canonical-property.md))</span></span>  <br/> |
|<span data-ttu-id="9683c-123">**PR_DISPLAY_NAME**([PidTagDisplayName](pidtagdisplayname-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="9683c-123">**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="9683c-124">**PR_DISPLAY_TYPE**([PidTagDisplayType](pidtagdisplaytype-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="9683c-124">**PR_DISPLAY_TYPE** ([PidTagDisplayType](pidtagdisplaytype-canonical-property.md))</span></span>  <br/> |
|<span data-ttu-id="9683c-125">**PR_ENTRYID**([PidTagEntryId](pidtagentryid-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="9683c-125">**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="9683c-126">**PR_INSTANCE_KEY**([PidTagInstanceKey](pidtaginstancekey-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="9683c-126">**PR_INSTANCE_KEY** ([PidTagInstanceKey](pidtaginstancekey-canonical-property.md))</span></span>  <br/> |
|<span data-ttu-id="9683c-127">**PR_OBJECT_TYPE**([PidTagObjectType](pidtagobjecttype-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="9683c-127">**PR_OBJECT_TYPE** ([PidTagObjectType](pidtagobjecttype-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="9683c-128">**PR_STATUS**([PidTagStatus](pidtagstatus-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="9683c-128">**PR_STATUS** ([PidTagStatus](pidtagstatus-canonical-property.md))</span></span>  <br/> |
   
 <span data-ttu-id="9683c-129">**PR_DISPLAY_NAME**包含应显示在层次结构显示中的容器或文件夹的名称。</span><span class="sxs-lookup"><span data-stu-id="9683c-129">**PR_DISPLAY_NAME** contains the name for the container or folder that should appear in the display of the hierarchy.</span></span> 
  
 <span data-ttu-id="9683c-130">**PR_ENTRYID**是与此容器或文件夹相关联的条目标识符。</span><span class="sxs-lookup"><span data-stu-id="9683c-130">**PR_ENTRYID** is the entry identifier associated with this container or folder.</span></span> <span data-ttu-id="9683c-131">它应为长期条目标识符。</span><span class="sxs-lookup"><span data-stu-id="9683c-131">It is expected to be a long-term entry identifier.</span></span> <span data-ttu-id="9683c-132">客户端和 MAPI 可以将此条目标识符传递给**OpenEntry** , 以打开容器或文件夹, 并通过调用[IMAPIContainer:: GetContentsTable](imapicontainer-getcontentstable.md)来查看其内容。</span><span class="sxs-lookup"><span data-stu-id="9683c-132">Clients and MAPI can pass this entry identifier to **OpenEntry** to open the container or folder and view its contents by calling [IMAPIContainer::GetContentsTable](imapicontainer-getcontentstable.md).</span></span> 
  
 <span data-ttu-id="9683c-133">**PR_DEPTH**是一个数值, 指示此容器或文件夹的缩进级别, 其中零为最高级别。</span><span class="sxs-lookup"><span data-stu-id="9683c-133">**PR_DEPTH** is a numeric value that indicates the level of indentation for this container or folder with zero being the top level.</span></span> <span data-ttu-id="9683c-134">容器或文件夹所在的层次结构中的深度越深, 其**PR_DEPTH**属性的值就越高。</span><span class="sxs-lookup"><span data-stu-id="9683c-134">The deeper in the hierarchy a container or folder resides, the higher the value for its **PR_DEPTH** property.</span></span> <span data-ttu-id="9683c-135">客户端使用**PR_DEPTH**属性来适当地显示层次结构表, 以便用户可以清楚地看到父关系和子关系。</span><span class="sxs-lookup"><span data-stu-id="9683c-135">Clients use the **PR_DEPTH** property to display a hierarchy table appropriately so that users can clearly see parent and child relationships.</span></span> <span data-ttu-id="9683c-136">容器或文件夹深度始终相对于实现层次结构表的容器或文件夹。</span><span class="sxs-lookup"><span data-stu-id="9683c-136">Container or folder depth is always relative to the container or folder implementing the hierarchy table.</span></span> 
  
 <span data-ttu-id="9683c-137">对于通讯簿层次结构表和 MAPI_FOLDER (对于文件夹层次结构表), **PR_OBJECT_TYPE**始终设置为 MAPI_ABCONT。</span><span class="sxs-lookup"><span data-stu-id="9683c-137">**PR_OBJECT_TYPE** is always set to MAPI_ABCONT for address book hierarchy tables and MAPI_FOLDER for folder hierarchy tables.</span></span> 
  
 <span data-ttu-id="9683c-138">**PR_DISPLAY_TYPE**是一个数字值, 它与容器或文件夹在层次结构表中的显示方式相关。</span><span class="sxs-lookup"><span data-stu-id="9683c-138">**PR_DISPLAY_TYPE** is a numeric value that relates to how a container or folder is displayed in the hierarchy table.</span></span> <span data-ttu-id="9683c-139">它主要用于显示目的, 以在容器或文件夹的类型之间进行区分。</span><span class="sxs-lookup"><span data-stu-id="9683c-139">It is mainly used for display purposes, to differentiate visually between types of containers or folders.</span></span> <span data-ttu-id="9683c-140">许多邮件存储和通讯簿提供程序将图标用于不同的显示类型。</span><span class="sxs-lookup"><span data-stu-id="9683c-140">Many message store and address book providers use icons for the different display types.</span></span> <span data-ttu-id="9683c-141">提供程序需要提供这些图标;MAPI 不提供默认值。</span><span class="sxs-lookup"><span data-stu-id="9683c-141">It is up to the provider to supply these icons; MAPI does not supply defaults.</span></span> 
  
<span data-ttu-id="9683c-142">MAPI 为**PR_DISPLAY_TYPE**定义了多个值, 有些值对与通讯簿容器的层次结构表一起使用的文件夹和其他值有效。</span><span class="sxs-lookup"><span data-stu-id="9683c-142">MAPI defines many values for **PR_DISPLAY_TYPE**, some that are valid for folders and others that are used with the hierarchy tables of address book containers.</span></span> <span data-ttu-id="9683c-143">通常情况下, 文件夹的**PR_DISPLAY_TYPE**设置为 DT_FOLDER, 以指示默认的文件夹图标、DT_FOLDER_LINK 指示表示指向另一个文件夹的链接的图标, 或 DT_FOLDER_SPECIAL 指示特定于应用程序的图标。</span><span class="sxs-lookup"><span data-stu-id="9683c-143">Typically, a folder's **PR_DISPLAY_TYPE** is set to DT_FOLDER to indicate a default folder icon, DT_FOLDER_LINK to indicate an icon that represents a link to another folder, or DT_FOLDER_SPECIAL to indicate an icon that is application-specific.</span></span> <span data-ttu-id="9683c-144">DT_FOLDER_LINK 与搜索结果文件夹一起使用。</span><span class="sxs-lookup"><span data-stu-id="9683c-144">DT_FOLDER_LINK is used with search-results folders.</span></span> 
  
<span data-ttu-id="9683c-145">除了这些必需的列之外, 通讯簿层次结构表必须包含**PR_CONTAINER_FLAGS**属性。</span><span class="sxs-lookup"><span data-stu-id="9683c-145">In addition to these required columns, address book hierarchy tables must include the **PR_CONTAINER_FLAGS** property.</span></span> <span data-ttu-id="9683c-146">**PR_CONTAINER_FLAGS**指示有关层次结构中的容器的各种属性, 并用于区分一个容器与另一个容器。</span><span class="sxs-lookup"><span data-stu-id="9683c-146">**PR_CONTAINER_FLAGS** indicates various attributes about a container in the hierarchy and is used to distinguish one container from another.</span></span> 
  
<span data-ttu-id="9683c-147">通讯簿层次结构表的可选属性是**PR_AB_PROVIDER_ID** ([PidTagAbProviderId](pidtagabproviderid-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="9683c-147">An optional property for address book hierarchy tables is the **PR_AB_PROVIDER_ID** ([PidTagAbProviderId](pidtagabproviderid-canonical-property.md)) property.</span></span>
  
<span data-ttu-id="9683c-148">邮件存储区层次结构表在其必需的列集中包含这些属性:</span><span class="sxs-lookup"><span data-stu-id="9683c-148">Message-store hierarchy tables include these properties in their required column set:</span></span>
  
- <span data-ttu-id="9683c-149">**PR_FOLDER_TYPE**([PidTagFolderType](pidtagfoldertype-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="9683c-149">**PR_FOLDER_TYPE** ([PidTagFolderType](pidtagfoldertype-canonical-property.md))</span></span>
    
- <span data-ttu-id="9683c-150">**PR_SUBFOLDERS**([PidTagSubfolders](pidtagsubfolders-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="9683c-150">**PR_SUBFOLDERS** ([PidTagSubfolders](pidtagsubfolders-canonical-property.md))</span></span>
    
- <span data-ttu-id="9683c-151">**PR_CONTENT_COUNT**([PidTagContentCount](pidtagcontentcount-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="9683c-151">**PR_CONTENT_COUNT** ([PidTagContentCount](pidtagcontentcount-canonical-property.md))</span></span>
    
- <span data-ttu-id="9683c-152">**PR_CONTENT_UNREAD**([PidTagContentUnreadCount](pidtagcontentunreadcount-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="9683c-152">**PR_CONTENT_UNREAD** ([PidTagContentUnreadCount](pidtagcontentunreadcount-canonical-property.md))</span></span>
    
<span data-ttu-id="9683c-153">通讯簿提供程序必须支持其层次结构表实现中的以下**IMAPITable**方法, 因为它们是 MAPI 集成通讯簿所必需的:</span><span class="sxs-lookup"><span data-stu-id="9683c-153">Address book providers must support the following **IMAPITable** methods in their hierarchy table implementations because they are required by the MAPI integrated address book:</span></span> 
  
|||
|:-----|:-----|
|[<span data-ttu-id="9683c-154">IMAPITable::QueryColumns</span><span class="sxs-lookup"><span data-stu-id="9683c-154">IMAPITable::QueryColumns</span></span>](imapitable-querycolumns.md) <br/> |[<span data-ttu-id="9683c-155">IMAPITable::QueryPosition</span><span class="sxs-lookup"><span data-stu-id="9683c-155">IMAPITable::QueryPosition</span></span>](imapitable-queryposition.md) <br/> |
|[<span data-ttu-id="9683c-156">IMAPITable::SeekRow</span><span class="sxs-lookup"><span data-stu-id="9683c-156">IMAPITable::SeekRow</span></span>](imapitable-seekrow.md) <br/> |[<span data-ttu-id="9683c-157">IMAPITable::SeekRowApprox</span><span class="sxs-lookup"><span data-stu-id="9683c-157">IMAPITable::SeekRowApprox</span></span>](imapitable-seekrowapprox.md) <br/> |
|[<span data-ttu-id="9683c-158">IMAPITable::FindRow</span><span class="sxs-lookup"><span data-stu-id="9683c-158">IMAPITable::FindRow</span></span>](imapitable-findrow.md) <br/> |[<span data-ttu-id="9683c-159">IMAPITable::Restrict</span><span class="sxs-lookup"><span data-stu-id="9683c-159">IMAPITable::Restrict</span></span>](imapitable-restrict.md) <br/> |
|[<span data-ttu-id="9683c-160">IMAPITable::CreateBookmark</span><span class="sxs-lookup"><span data-stu-id="9683c-160">IMAPITable::CreateBookmark</span></span>](imapitable-createbookmark.md) <br/> |[<span data-ttu-id="9683c-161">IMAPITable::FreeBookmark</span><span class="sxs-lookup"><span data-stu-id="9683c-161">IMAPITable::FreeBookmark</span></span>](imapitable-freebookmark.md) <br/> |
|[<span data-ttu-id="9683c-162">IMAPITable::QueryRows</span><span class="sxs-lookup"><span data-stu-id="9683c-162">IMAPITable::QueryRows</span></span>](imapitable-queryrows.md) <br/> | <br/> |
   
## <a name="see-also"></a><span data-ttu-id="9683c-163">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9683c-163">See also</span></span>



[<span data-ttu-id="9683c-164">MAPI 表</span><span class="sxs-lookup"><span data-stu-id="9683c-164">MAPI Tables</span></span>](mapi-tables.md)

