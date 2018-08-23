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
ms.openlocfilehash: d135e0c224866cd2a675df2ef9ec1b206f3169ab
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22580752"
---
# <a name="hierarchy-tables"></a><span data-ttu-id="28548-103">层次结构表</span><span class="sxs-lookup"><span data-stu-id="28548-103">Hierarchy Tables</span></span>

  
  
<span data-ttu-id="28548-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="28548-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="28548-105">层次结构表包含有关邮件存储区中的文件夹或通讯簿容器中的容器的信息。</span><span class="sxs-lookup"><span data-stu-id="28548-105">A hierarchy table contains information about the folders in a message store or the containers in an address book container.</span></span> <span data-ttu-id="28548-106">层次结构表的每一行包含一组与一个文件夹或通讯簿容器信息的列。</span><span class="sxs-lookup"><span data-stu-id="28548-106">Each row of a hierarchy table contains a set of columns with information about one folder or address book container.</span></span> <span data-ttu-id="28548-107">层次结构表主要由客户端使用和消息存储提供程序以显示的文件夹和子文件夹树由实现并由通讯簿提供程序以在通讯簿中显示的容器树实现。</span><span class="sxs-lookup"><span data-stu-id="28548-107">Hierarchy tables are primarily used by clients and implemented by message store providers to show a tree of folders and subfolders and implemented by address book providers to show a tree of containers in the address book.</span></span> <span data-ttu-id="28548-108">容器不能容纳子容器，由缺少其**PR_CONTAINER_FLAGS** ([PidTagContainerFlags](pidtagcontainerflags-canonical-property.md)) 属性中，AB_SUBCONTAINERS 标志不实现层次结构表。</span><span class="sxs-lookup"><span data-stu-id="28548-108">Containers that cannot hold subcontainers, as indicated by the absence of the AB_SUBCONTAINERS flag in their **PR_CONTAINER_FLAGS** ([PidTagContainerFlags](pidtagcontainerflags-canonical-property.md)) property, do not implement a hierarchy table.</span></span>
  
<span data-ttu-id="28548-109">可以通过调用访问层次结构表：</span><span class="sxs-lookup"><span data-stu-id="28548-109">A hierarchy table can be accessed by calling:</span></span>
  
- <span data-ttu-id="28548-110">[IMAPIContainer::GetHierarchyTable](imapicontainer-gethierarchytable.md)。</span><span class="sxs-lookup"><span data-stu-id="28548-110">[IMAPIContainer::GetHierarchyTable](imapicontainer-gethierarchytable.md).</span></span>
    
    - <span data-ttu-id="28548-111">或者-</span><span class="sxs-lookup"><span data-stu-id="28548-111">Or -</span></span>
    
- <span data-ttu-id="28548-112">[IMAPIProp::OpenProperty](imapiprop-openproperty.md)作为属性标记和 IID_IMAPITable 接口标识传递**PR_CONTAINER_HIERARCHY** ([PidTagContainerHierarchy](pidtagcontainerhierarchy-canonical-property.md))。</span><span class="sxs-lookup"><span data-stu-id="28548-112">[IMAPIProp::OpenProperty](imapiprop-openproperty.md) passing **PR_CONTAINER_HIERARCHY** ([PidTagContainerHierarchy](pidtagcontainerhierarchy-canonical-property.md)) as the property tag and IID_IMAPITable as the interface identifier.</span></span>
    
<span data-ttu-id="28548-113">容器和文件夹必须支持这两种方法，用于检索表属性。</span><span class="sxs-lookup"><span data-stu-id="28548-113">Containers and folders must support both techniques for retrieving table properties.</span></span> <span data-ttu-id="28548-114">无法接受的服务提供商支持只有一个办法可以访问这些表，因为客户端期望有选择它。</span><span class="sxs-lookup"><span data-stu-id="28548-114">It is unacceptable for service providers to support only one way to access these tables because clients expect to have the choice.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="28548-115">存储提供程序不能保证服从设置指定的层次结构表的排序次序。</span><span class="sxs-lookup"><span data-stu-id="28548-115">Store providers are not guaranteed to honor the sort order set specified for hierarchy tables.</span></span> 
  
<span data-ttu-id="28548-116">调用**IMAPIProp::OpenProperty**涉及通过打开及其对应的属性， **PR_CONTAINER_HIERARCHY**访问层次结构表。</span><span class="sxs-lookup"><span data-stu-id="28548-116">The call to **IMAPIProp::OpenProperty** involves accessing the hierarchy table by opening its corresponding property, **PR_CONTAINER_HIERARCHY**.</span></span> <span data-ttu-id="28548-117">尽管**PR_CONTAINER_HIERARCHY**无法检索到的文件夹或容器的[IMAPIProp::GetProps](imapiprop-getprops.md)方法，它包含由[IMAPIProp::GetPropList](imapiprop-getproplist.md)方法返回的属性标记数组。</span><span class="sxs-lookup"><span data-stu-id="28548-117">Although **PR_CONTAINER_HIERARCHY** cannot be retrieved through a folder or container's [IMAPIProp::GetProps](imapiprop-getprops.md) method, it is included in the property tag array that is returned by the [IMAPIProp::GetPropList](imapiprop-getproplist.md) method.</span></span> 
  
 <span data-ttu-id="28548-118">**PR_CONTAINER_HIERARCHY**还可以用于中包括或排除层次结构表复制操作。</span><span class="sxs-lookup"><span data-stu-id="28548-118">**PR_CONTAINER_HIERARCHY** can also be used to include or exclude a hierarchy table from a copy operation.</span></span> <span data-ttu-id="28548-119">如果客户端**PR_CONTAINER_HIERARCHY** *lpExcludeProps*参数中指定的[IMAPIProp::CopyTo](imapiprop-copyto.md)复制操作中的新文件夹或容器不支持的原始文件夹或容器的层次结构表。</span><span class="sxs-lookup"><span data-stu-id="28548-119">If a client specifies **PR_CONTAINER_HIERARCHY** in the  *lpExcludeProps*  parameter for [IMAPIProp::CopyTo](imapiprop-copyto.md) in a copy operation, the new folder or container will not support the hierarchy table of the original folder or container.</span></span> 
  
<span data-ttu-id="28548-120">以下属性组成层次结构表中设置所需的列：</span><span class="sxs-lookup"><span data-stu-id="28548-120">The following properties make up the required column set in a hierarchy table:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="28548-121">**PR_COMMENT**([PidTagComment](pidtagcomment-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="28548-121">**PR_COMMENT** ([PidTagComment](pidtagcomment-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="28548-122">**PR_DEPTH**([PidTagDepth](pidtagdepth-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="28548-122">**PR_DEPTH** ([PidTagDepth](pidtagdepth-canonical-property.md))</span></span>  <br/> |
|<span data-ttu-id="28548-123">**PR_DISPLAY_NAME**([PidTagDisplayName](pidtagdisplayname-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="28548-123">**PR_DISPLAY_NAME** ([PidTagDisplayName](pidtagdisplayname-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="28548-124">**PR_DISPLAY_TYPE**([PidTagDisplayType](pidtagdisplaytype-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="28548-124">**PR_DISPLAY_TYPE** ([PidTagDisplayType](pidtagdisplaytype-canonical-property.md))</span></span>  <br/> |
|<span data-ttu-id="28548-125">**PR_ENTRYID**([PidTagEntryId](pidtagentryid-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="28548-125">**PR_ENTRYID** ([PidTagEntryId](pidtagentryid-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="28548-126">**PR_INSTANCE_KEY**([PidTagInstanceKey](pidtaginstancekey-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="28548-126">**PR_INSTANCE_KEY** ([PidTagInstanceKey](pidtaginstancekey-canonical-property.md))</span></span>  <br/> |
|<span data-ttu-id="28548-127">**PR_OBJECT_TYPE**([PidTagObjectType](pidtagobjecttype-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="28548-127">**PR_OBJECT_TYPE** ([PidTagObjectType](pidtagobjecttype-canonical-property.md))</span></span>  <br/> |<span data-ttu-id="28548-128">**PR_STATUS**([PidTagStatus](pidtagstatus-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="28548-128">**PR_STATUS** ([PidTagStatus](pidtagstatus-canonical-property.md))</span></span>  <br/> |
   
 <span data-ttu-id="28548-129">**PR_DISPLAY_NAME**包含容器或应出现在显示的层次结构的文件夹的名称。</span><span class="sxs-lookup"><span data-stu-id="28548-129">**PR_DISPLAY_NAME** contains the name for the container or folder that should appear in the display of the hierarchy.</span></span> 
  
 <span data-ttu-id="28548-130">**PR_ENTRYID**是与此容器或文件夹关联的项标识符。</span><span class="sxs-lookup"><span data-stu-id="28548-130">**PR_ENTRYID** is the entry identifier associated with this container or folder.</span></span> <span data-ttu-id="28548-131">它将是长期的项标识符。</span><span class="sxs-lookup"><span data-stu-id="28548-131">It is expected to be a long-term entry identifier.</span></span> <span data-ttu-id="28548-132">客户端和 MAPI 可以传递给**OpenEntry**打开的容器或文件夹并通过调用[IMAPIContainer::GetContentsTable](imapicontainer-getcontentstable.md)查看其内容的此条目标识符。</span><span class="sxs-lookup"><span data-stu-id="28548-132">Clients and MAPI can pass this entry identifier to **OpenEntry** to open the container or folder and view its contents by calling [IMAPIContainer::GetContentsTable](imapicontainer-getcontentstable.md).</span></span> 
  
 <span data-ttu-id="28548-133">**PR_DEPTH**是零正在顶级指示此容器或文件夹的缩进级别的数值。</span><span class="sxs-lookup"><span data-stu-id="28548-133">**PR_DEPTH** is a numeric value that indicates the level of indentation for this container or folder with zero being the top level.</span></span> <span data-ttu-id="28548-134">更深入的容器或文件夹层次结构中位于，其**PR_DEPTH**属性的值越高。</span><span class="sxs-lookup"><span data-stu-id="28548-134">The deeper in the hierarchy a container or folder resides, the higher the value for its **PR_DEPTH** property.</span></span> <span data-ttu-id="28548-135">客户端使用**PR_DEPTH**属性，以便用户可以清楚地查看父级和子级关系适当地显示层次结构表。</span><span class="sxs-lookup"><span data-stu-id="28548-135">Clients use the **PR_DEPTH** property to display a hierarchy table appropriately so that users can clearly see parent and child relationships.</span></span> <span data-ttu-id="28548-136">容器或文件夹深度始终是相对于容器或实现层次结构表的文件夹。</span><span class="sxs-lookup"><span data-stu-id="28548-136">Container or folder depth is always relative to the container or folder implementing the hierarchy table.</span></span> 
  
 <span data-ttu-id="28548-137">**PR_OBJECT_TYPE**始终设置为 MAPI_ABCONT 通讯簿层次结构表和 MAPI_FOLDER 的文件夹层次结构表。</span><span class="sxs-lookup"><span data-stu-id="28548-137">**PR_OBJECT_TYPE** is always set to MAPI_ABCONT for address book hierarchy tables and MAPI_FOLDER for folder hierarchy tables.</span></span> 
  
 <span data-ttu-id="28548-138">**PR_DISPLAY_TYPE**是一个数值，它与容器或文件夹的层次结构表的显示方式。</span><span class="sxs-lookup"><span data-stu-id="28548-138">**PR_DISPLAY_TYPE** is a numeric value that relates to how a container or folder is displayed in the hierarchy table.</span></span> <span data-ttu-id="28548-139">它主要用于显示出于，直观地区分类型的容器或文件夹。</span><span class="sxs-lookup"><span data-stu-id="28548-139">It is mainly used for display purposes, to differentiate visually between types of containers or folders.</span></span> <span data-ttu-id="28548-140">许多消息存储和通讯簿提供程序使用不同的显示类型的图标。</span><span class="sxs-lookup"><span data-stu-id="28548-140">Many message store and address book providers use icons for the different display types.</span></span> <span data-ttu-id="28548-141">由要提供这些图标; 的提供程序MAPI 不会提供默认值。</span><span class="sxs-lookup"><span data-stu-id="28548-141">It is up to the provider to supply these icons; MAPI does not supply defaults.</span></span> 
  
<span data-ttu-id="28548-142">MAPI 定义**PR_DISPLAY_TYPE**的有效的文件夹和其他人的地址簿容器层次结构表与使用多个值。</span><span class="sxs-lookup"><span data-stu-id="28548-142">MAPI defines many values for **PR_DISPLAY_TYPE**, some that are valid for folders and others that are used with the hierarchy tables of address book containers.</span></span> <span data-ttu-id="28548-143">通常，某个文件夹的**PR_DISPLAY_TYPE**设置为 DT_FOLDER 以指示默认文件夹图标，DT_FOLDER_LINK 以指示图标表示指向另一个文件夹或 DT_FOLDER_SPECIAL 以指示特定于应用程序的图标。</span><span class="sxs-lookup"><span data-stu-id="28548-143">Typically, a folder's **PR_DISPLAY_TYPE** is set to DT_FOLDER to indicate a default folder icon, DT_FOLDER_LINK to indicate an icon that represents a link to another folder, or DT_FOLDER_SPECIAL to indicate an icon that is application-specific.</span></span> <span data-ttu-id="28548-144">DT_FOLDER_LINK 用于搜索结果文件夹。</span><span class="sxs-lookup"><span data-stu-id="28548-144">DT_FOLDER_LINK is used with search-results folders.</span></span> 
  
<span data-ttu-id="28548-145">除了这些所需的列，通讯簿层次结构表必须包括**PR_CONTAINER_FLAGS**属性。</span><span class="sxs-lookup"><span data-stu-id="28548-145">In addition to these required columns, address book hierarchy tables must include the **PR_CONTAINER_FLAGS** property.</span></span> <span data-ttu-id="28548-146">**PR_CONTAINER_FLAGS**指示有关容器层次结构中的各种属性，用于区分从另一个容器。</span><span class="sxs-lookup"><span data-stu-id="28548-146">**PR_CONTAINER_FLAGS** indicates various attributes about a container in the hierarchy and is used to distinguish one container from another.</span></span> 
  
<span data-ttu-id="28548-147">通讯簿层次结构表可选属性是**PR_AB_PROVIDER_ID** ([PidTagAbProviderId](pidtagabproviderid-canonical-property.md)) 属性。</span><span class="sxs-lookup"><span data-stu-id="28548-147">An optional property for address book hierarchy tables is the **PR_AB_PROVIDER_ID** ([PidTagAbProviderId](pidtagabproviderid-canonical-property.md)) property.</span></span>
  
<span data-ttu-id="28548-148">消息存储层次结构表在其所需的列集包含以下属性：</span><span class="sxs-lookup"><span data-stu-id="28548-148">Message-store hierarchy tables include these properties in their required column set:</span></span>
  
- <span data-ttu-id="28548-149">**PR_FOLDER_TYPE**([PidTagFolderType](pidtagfoldertype-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="28548-149">**PR_FOLDER_TYPE** ([PidTagFolderType](pidtagfoldertype-canonical-property.md))</span></span>
    
- <span data-ttu-id="28548-150">**PR_SUBFOLDERS**([PidTagSubfolders](pidtagsubfolders-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="28548-150">**PR_SUBFOLDERS** ([PidTagSubfolders](pidtagsubfolders-canonical-property.md))</span></span>
    
- <span data-ttu-id="28548-151">**PR_CONTENT_COUNT**([PidTagContentCount](pidtagcontentcount-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="28548-151">**PR_CONTENT_COUNT** ([PidTagContentCount](pidtagcontentcount-canonical-property.md))</span></span>
    
- <span data-ttu-id="28548-152">**PR_CONTENT_UNREAD**([PidTagContentUnreadCount](pidtagcontentunreadcount-canonical-property.md))</span><span class="sxs-lookup"><span data-stu-id="28548-152">**PR_CONTENT_UNREAD** ([PidTagContentUnreadCount](pidtagcontentunreadcount-canonical-property.md))</span></span>
    
<span data-ttu-id="28548-153">通讯簿提供程序必须在其层次结构表实现中支持下列**IMAPITable**方法，因为它们所需的 MAPI 集成的通讯簿：</span><span class="sxs-lookup"><span data-stu-id="28548-153">Address book providers must support the following **IMAPITable** methods in their hierarchy table implementations because they are required by the MAPI integrated address book:</span></span> 
  
|||
|:-----|:-----|
|[<span data-ttu-id="28548-154">IMAPITable::QueryColumns</span><span class="sxs-lookup"><span data-stu-id="28548-154">IMAPITable::QueryColumns</span></span>](imapitable-querycolumns.md) <br/> |[<span data-ttu-id="28548-155">IMAPITable::QueryPosition</span><span class="sxs-lookup"><span data-stu-id="28548-155">IMAPITable::QueryPosition</span></span>](imapitable-queryposition.md) <br/> |
|[<span data-ttu-id="28548-156">IMAPITable::SeekRow</span><span class="sxs-lookup"><span data-stu-id="28548-156">IMAPITable::SeekRow</span></span>](imapitable-seekrow.md) <br/> |[<span data-ttu-id="28548-157">IMAPITable::SeekRowApprox</span><span class="sxs-lookup"><span data-stu-id="28548-157">IMAPITable::SeekRowApprox</span></span>](imapitable-seekrowapprox.md) <br/> |
|[<span data-ttu-id="28548-158">IMAPITable::FindRow</span><span class="sxs-lookup"><span data-stu-id="28548-158">IMAPITable::FindRow</span></span>](imapitable-findrow.md) <br/> |[<span data-ttu-id="28548-159">IMAPITable::Restrict</span><span class="sxs-lookup"><span data-stu-id="28548-159">IMAPITable::Restrict</span></span>](imapitable-restrict.md) <br/> |
|[<span data-ttu-id="28548-160">IMAPITable::CreateBookmark</span><span class="sxs-lookup"><span data-stu-id="28548-160">IMAPITable::CreateBookmark</span></span>](imapitable-createbookmark.md) <br/> |[<span data-ttu-id="28548-161">IMAPITable::FreeBookmark</span><span class="sxs-lookup"><span data-stu-id="28548-161">IMAPITable::FreeBookmark</span></span>](imapitable-freebookmark.md) <br/> |
|[<span data-ttu-id="28548-162">IMAPITable::QueryRows</span><span class="sxs-lookup"><span data-stu-id="28548-162">IMAPITable::QueryRows</span></span>](imapitable-queryrows.md) <br/> | <br/> |
   
## <a name="see-also"></a><span data-ttu-id="28548-163">另请参阅</span><span class="sxs-lookup"><span data-stu-id="28548-163">See also</span></span>



[<span data-ttu-id="28548-164">MAPI 表</span><span class="sxs-lookup"><span data-stu-id="28548-164">MAPI Tables</span></span>](mapi-tables.md)

