---
title: Display Server Folder Sizes 属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- Display Server Folder Sizes Property
api_type:
- COM
ms.assetid: 38429fdb-be93-213a-a780-80f9837f55fa
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 85a8b5216eac1dd4e4cebd1313cb31c9b5d70227
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33434548"
---
# <a name="display-server-folder-sizes-property"></a><span data-ttu-id="17dcd-103">Display Server Folder Sizes 属性</span><span class="sxs-lookup"><span data-stu-id="17dcd-103">Display Server Folder Sizes Property</span></span>

  
  
<span data-ttu-id="17dcd-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="17dcd-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="17dcd-105">在"文件夹大小"对话框中显示Outlook **指定** 文件夹的大小。</span><span class="sxs-lookup"><span data-stu-id="17dcd-105">Displays the sizes of specified folders on the server in the Outlook **Folder Size** dialog box.</span></span> 
  
## <a name="quick-info"></a><span data-ttu-id="17dcd-106">快速信息</span><span class="sxs-lookup"><span data-stu-id="17dcd-106">Quick info</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="17dcd-107">在：</span><span class="sxs-lookup"><span data-stu-id="17dcd-107">Exposed on:</span></span>  <br/> |<span data-ttu-id="17dcd-108">[IMsgStore ： IMAPIProp](imsgstoreimapiprop.md) 对象</span><span class="sxs-lookup"><span data-stu-id="17dcd-108">[IMsgStore : IMAPIProp](imsgstoreimapiprop.md) object</span></span>  <br/> |
|<span data-ttu-id="17dcd-109">创建者：</span><span class="sxs-lookup"><span data-stu-id="17dcd-109">Created by:</span></span>  <br/> |<span data-ttu-id="17dcd-110">存储提供程序</span><span class="sxs-lookup"><span data-stu-id="17dcd-110">Store provider</span></span>  <br/> |
|<span data-ttu-id="17dcd-111">访问者：</span><span class="sxs-lookup"><span data-stu-id="17dcd-111">Accessed by:</span></span>  <br/> |<span data-ttu-id="17dcd-112">Outlook客户端和其他客户端</span><span class="sxs-lookup"><span data-stu-id="17dcd-112">Outlook and other clients</span></span>  <br/> |
|<span data-ttu-id="17dcd-113">属性类型</span><span class="sxs-lookup"><span data-stu-id="17dcd-113">Property type:</span></span>  <br/> |<span data-ttu-id="17dcd-114">PT_BOOLEAN</span><span class="sxs-lookup"><span data-stu-id="17dcd-114">PT_BOOLEAN</span></span>  <br/> |
|<span data-ttu-id="17dcd-115">访问类型：</span><span class="sxs-lookup"><span data-stu-id="17dcd-115">Access type:</span></span>  <br/> |<span data-ttu-id="17dcd-116">读/写</span><span class="sxs-lookup"><span data-stu-id="17dcd-116">Read/write</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="17dcd-117">备注</span><span class="sxs-lookup"><span data-stu-id="17dcd-117">Remarks</span></span>

<span data-ttu-id="17dcd-118">若要提供任何存储功能，存储提供程序必须实现 [IMAPIProp ： IUnknown](imapipropiunknown.md) 并返回传递给 [IMAPIProp：：GetIDsFromNames](imapiprop-getidsfromnames.md) 调用的任何属性的有效属性标记。</span><span class="sxs-lookup"><span data-stu-id="17dcd-118">To provide any of the store functionality, the store provider must implement [IMAPIProp : IUnknown](imapipropiunknown.md) and return a valid property tag for any of these properties passed to an [IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md) call.</span></span> <span data-ttu-id="17dcd-119">当其中任何属性的属性标记传递到 [IMAPIProp：：GetProps](imapiprop-getprops.md)时，存储提供程序还必须返回正确的属性值。</span><span class="sxs-lookup"><span data-stu-id="17dcd-119">When the property tag for any of these properties is passed to [IMAPIProp::GetProps](imapiprop-getprops.md), the store provider must also return the correct property value.</span></span> <span data-ttu-id="17dcd-120">存储提供程序可以调用 [HrGetOneProp](hrgetoneprop.md) 和 [HrSetOneProp](hrsetoneprop.md) 获取或设置这些属性。</span><span class="sxs-lookup"><span data-stu-id="17dcd-120">Store providers can call [HrGetOneProp](hrgetoneprop.md) and [HrSetOneProp](hrsetoneprop.md) to get or set these properties.</span></span> 
  
<span data-ttu-id="17dcd-121">若要检索此属性的值，客户端应首先使用 [IMAPIProp：：GetIDsFromNames](imapiprop-getidsfromnames.md) 获取属性标记，然后在 [IMAPIProp：：GetProps](imapiprop-getprops.md) 中指定此属性标记以获取值。</span><span class="sxs-lookup"><span data-stu-id="17dcd-121">To retrieve the value of this property, the client should first use [IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md) to obtain the property tag, and then specify this property tag in [IMAPIProp::GetProps](imapiprop-getprops.md) to get the value.</span></span> <span data-ttu-id="17dcd-122">调用 [IMAPIProp：：GetIDsFromNames](imapiprop-getidsfromnames.md)时，为输入参数 _lppPropNames_ 指向的 [MAPINAMEID](mapinameid.md)结构指定以下值：</span><span class="sxs-lookup"><span data-stu-id="17dcd-122">When calling [IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md), specify the following values for the [MAPINAMEID](mapinameid.md) structure pointed at by the input parameter  _lppPropNames_:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="17dcd-123">lpGuid：</span><span class="sxs-lookup"><span data-stu-id="17dcd-123">lpGuid:</span></span>  <br/> |<span data-ttu-id="17dcd-124">PS_PUBLIC_STRINGS</span><span class="sxs-lookup"><span data-stu-id="17dcd-124">PS_PUBLIC_STRINGS</span></span>  <br/> |
|<span data-ttu-id="17dcd-125">ulKind：</span><span class="sxs-lookup"><span data-stu-id="17dcd-125">ulKind:</span></span>  <br/> |<span data-ttu-id="17dcd-126">MNID_STRING</span><span class="sxs-lookup"><span data-stu-id="17dcd-126">MNID_STRING</span></span>  <br/> |
|<span data-ttu-id="17dcd-127">Kind.lpwstrName：</span><span class="sxs-lookup"><span data-stu-id="17dcd-127">Kind.lpwstrName:</span></span>  <br/> |<span data-ttu-id="17dcd-128">L"urn：schemas-microsoft-com：office：outlook#serverfoldersizes"</span><span class="sxs-lookup"><span data-stu-id="17dcd-128">L"urn:schemas-microsoft-com:office:outlook#serverfoldersizes"</span></span>  <br/> |
   
<span data-ttu-id="17dcd-129">此属性在 Microsoft Outlook 2003 Service Pack (SP) 1 中受支持。</span><span class="sxs-lookup"><span data-stu-id="17dcd-129">This property is supported in Microsoft Outlook 2003 Service Pack (SP) 1.</span></span> <span data-ttu-id="17dcd-130">如果 Outlook 的版本早于 Outlook 2003 SP 1，或者其值为 **false，Outlook** 将仅显示本地存储上文件夹的大小。</span><span class="sxs-lookup"><span data-stu-id="17dcd-130">If the version of Outlook is earlier than Outlook 2003 SP 1, or if its value is **false**, Outlook will display only the sizes of folders on the local store.</span></span> <span data-ttu-id="17dcd-131">如果在使用 Outlook 2003 SP 1 的存储区上设置此属性，Outlook 将查询服务器和本地驱动器上每个指定文件夹的大小。</span><span class="sxs-lookup"><span data-stu-id="17dcd-131">If this property is set on a store that uses Outlook 2003 SP 1, Outlook will query for the size of each specified folder on the server and the local drive.</span></span> 
  
<span data-ttu-id="17dcd-132">若要在服务器上查询文件夹大小，Outlook [使用 IMsgStore：：OpenEntry](imsgstore-openentry.md)打开存储区上的文件夹，并传递标志 **MAPI_NO_CACHE**，然后查询 PR_MESSAGE_SIZE_EXTENDED **。**</span><span class="sxs-lookup"><span data-stu-id="17dcd-132">To query for the folder size on the server, Outlook opens a folder on the store with [IMsgStore::OpenEntry](imsgstore-openentry.md), passing the flag **MAPI_NO_CACHE**, and then it queries for **PR_MESSAGE_SIZE_EXTENDED**.</span></span> <span data-ttu-id="17dcd-133">然后，存储提供程序应在服务器上返回文件夹大小。</span><span class="sxs-lookup"><span data-stu-id="17dcd-133">The store provider should then return the folder size on the server.</span></span>
  
<span data-ttu-id="17dcd-134">若要查询本地驱动器上文件夹的大小，Outlook打开不带 MAPI_NO_CACHE **标志的文件夹**。</span><span class="sxs-lookup"><span data-stu-id="17dcd-134">To query for the size of a folder on the local drive, Outlook opens the folder without the **MAPI_NO_CACHE** flag.</span></span> <span data-ttu-id="17dcd-135">然后，它将 **查询PR_MESSAGE_SIZE_EXTENDED**;存储提供程序应返回本地驱动器上指定文件夹的大小。</span><span class="sxs-lookup"><span data-stu-id="17dcd-135">It then queries for **PR_MESSAGE_SIZE_EXTENDED**; the store provider should return the size of the specified folder on the local drive.</span></span>
  
<span data-ttu-id="17dcd-136">通过设置此属性，将存储内容同步到服务器的存储提供程序显示文件夹"文件夹大小"对话框中Outlook **服务器上存储** 大小数据。</span><span class="sxs-lookup"><span data-stu-id="17dcd-136">With this property set, store providers that synchronize store contents to a server can display folder size data on the server in the Outlook **Folder Size** dialog box.</span></span> <span data-ttu-id="17dcd-137">然后，用户可以将其当前服务器存储使用情况与服务器配额进行比较。</span><span class="sxs-lookup"><span data-stu-id="17dcd-137">Users can then compare their current server storage usage with server quotas.</span></span> 
  

