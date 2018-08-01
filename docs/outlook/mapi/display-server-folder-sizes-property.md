---
title: 显示服务器文件夹大小属性
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
ms.openlocfilehash: 1ddf4501918d598169a3a74fd1c8d2ac38499cd2
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774798"
---
# <a name="display-server-folder-sizes-property"></a><span data-ttu-id="c2c27-103">显示服务器文件夹大小属性</span><span class="sxs-lookup"><span data-stu-id="c2c27-103">Display Server Folder Sizes Property</span></span>

  
  
<span data-ttu-id="c2c27-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="c2c27-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="c2c27-105">显示 Outlook**文件夹大小**对话框中的服务器上的指定文件夹的大小。</span><span class="sxs-lookup"><span data-stu-id="c2c27-105">Displays the sizes of specified folders on the server in the Outlook **Folder Size** dialog box.</span></span> 
  
## <a name="quick-info"></a><span data-ttu-id="c2c27-106">快速信息</span><span class="sxs-lookup"><span data-stu-id="c2c27-106">Quick info</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="c2c27-107">公开上：</span><span class="sxs-lookup"><span data-stu-id="c2c27-107">Exposed on:</span></span>  <br/> |<span data-ttu-id="c2c27-108">[IMsgStore: IMAPIProp](imsgstoreimapiprop.md)对象</span><span class="sxs-lookup"><span data-stu-id="c2c27-108">[IMsgStore : IMAPIProp](imsgstoreimapiprop.md) object</span></span>  <br/> |
|<span data-ttu-id="c2c27-109">通过创建：</span><span class="sxs-lookup"><span data-stu-id="c2c27-109">Created by:</span></span>  <br/> |<span data-ttu-id="c2c27-110">存储提供程序</span><span class="sxs-lookup"><span data-stu-id="c2c27-110">Store provider</span></span>  <br/> |
|<span data-ttu-id="c2c27-111">通过来访问：</span><span class="sxs-lookup"><span data-stu-id="c2c27-111">Accessed by:</span></span>  <br/> |<span data-ttu-id="c2c27-112">Outlook 和其他客户端</span><span class="sxs-lookup"><span data-stu-id="c2c27-112">Outlook and other clients</span></span>  <br/> |
|<span data-ttu-id="c2c27-113">属性类型</span><span class="sxs-lookup"><span data-stu-id="c2c27-113">Property type:</span></span>  <br/> |<span data-ttu-id="c2c27-114">PT_BOOLEAN</span><span class="sxs-lookup"><span data-stu-id="c2c27-114">PT_BOOLEAN</span></span>  <br/> |
|<span data-ttu-id="c2c27-115">访问类型：</span><span class="sxs-lookup"><span data-stu-id="c2c27-115">Access type:</span></span>  <br/> |<span data-ttu-id="c2c27-116">读/写</span><span class="sxs-lookup"><span data-stu-id="c2c27-116">Read/write</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="c2c27-117">备注</span><span class="sxs-lookup"><span data-stu-id="c2c27-117">Remarks</span></span>

<span data-ttu-id="c2c27-118">若要提供的任何存储功能，存储提供程序必须实现[IMAPIProp: IUnknown](imapipropiunknown.md)并返回任何传递给[IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md)调用这些属性的有效属性标记。</span><span class="sxs-lookup"><span data-stu-id="c2c27-118">To provide any of the store functionality, the store provider must implement [IMAPIProp : IUnknown](imapipropiunknown.md) and return a valid property tag for any of these properties passed to an [IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md) call.</span></span> <span data-ttu-id="c2c27-119">当属性标记为任何这些属性传递给[IMAPIProp::GetProps](imapiprop-getprops.md)时，存储提供程序必须也会返回正确的属性值。</span><span class="sxs-lookup"><span data-stu-id="c2c27-119">When the property tag for any of these properties is passed to [IMAPIProp::GetProps](imapiprop-getprops.md), the store provider must also return the correct property value.</span></span> <span data-ttu-id="c2c27-120">[HrGetOneProp](hrgetoneprop.md)和[HrSetOneProp](hrsetoneprop.md)用于获取或设置这些属性，可以调用存储提供程序。</span><span class="sxs-lookup"><span data-stu-id="c2c27-120">Store providers can call [HrGetOneProp](hrgetoneprop.md) and [HrSetOneProp](hrsetoneprop.md) to get or set these properties.</span></span> 
  
<span data-ttu-id="c2c27-121">若要检索此属性的值，客户应首先使用[IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md)获取该属性标记，然后[IMAPIProp::GetProps](imapiprop-getprops.md)获取值中指定此属性标记。</span><span class="sxs-lookup"><span data-stu-id="c2c27-121">To retrieve the value of this property, the client should first use [IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md) to obtain the property tag, and then specify this property tag in [IMAPIProp::GetProps](imapiprop-getprops.md) to get the value.</span></span> <span data-ttu-id="c2c27-122">调用[IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md)时, 指定的输入的参数_lppPropNames_指向[MAPINAMEID](mapinameid.md)结构的以下值：</span><span class="sxs-lookup"><span data-stu-id="c2c27-122">When calling [IMAPIProp::GetIDsFromNames](imapiprop-getidsfromnames.md), specify the following values for the [MAPINAMEID](mapinameid.md) structure pointed at by the input parameter  _lppPropNames_:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="c2c27-123">lpGuid:</span><span class="sxs-lookup"><span data-stu-id="c2c27-123">lpGuid:</span></span>  <br/> |<span data-ttu-id="c2c27-124">PS_PUBLIC_STRINGS</span><span class="sxs-lookup"><span data-stu-id="c2c27-124">PS_PUBLIC_STRINGS</span></span>  <br/> |
|<span data-ttu-id="c2c27-125">ulKind:</span><span class="sxs-lookup"><span data-stu-id="c2c27-125">ulKind:</span></span>  <br/> |<span data-ttu-id="c2c27-126">MNID_STRING</span><span class="sxs-lookup"><span data-stu-id="c2c27-126">MNID_STRING</span></span>  <br/> |
|<span data-ttu-id="c2c27-127">Kind.lpwstrName:</span><span class="sxs-lookup"><span data-stu-id="c2c27-127">Kind.lpwstrName:</span></span>  <br/> |<span data-ttu-id="c2c27-128">L"urn： 架构-microsoft-com:office:outlook #serverfoldersizes"</span><span class="sxs-lookup"><span data-stu-id="c2c27-128">L"urn:schemas-microsoft-com:office:outlook#serverfoldersizes"</span></span>  <br/> |
   
<span data-ttu-id="c2c27-129">在 Microsoft Outlook 2003 Service Pack (SP) 1年支持此属性。</span><span class="sxs-lookup"><span data-stu-id="c2c27-129">This property is supported in Microsoft Outlook 2003 Service Pack (SP) 1.</span></span> <span data-ttu-id="c2c27-130">如果 Outlook 版本早于 Outlook 2003 SP 1，或其值为**false**，则 Outlook 将上本地存储中显示文件夹的大小。</span><span class="sxs-lookup"><span data-stu-id="c2c27-130">If the version of Outlook is earlier than Outlook 2003 SP 1, or if its value is **false**, Outlook will display only the sizes of folders on the local store.</span></span> <span data-ttu-id="c2c27-131">如果此属性设置在使用 Outlook 2003 SP 1 的存储区上，Outlook 将查询服务器和本地驱动器上的每个指定文件夹的大小。</span><span class="sxs-lookup"><span data-stu-id="c2c27-131">If this property is set on a store that uses Outlook 2003 SP 1, Outlook will query for the size of each specified folder on the server and the local drive.</span></span> 
  
<span data-ttu-id="c2c27-132">查询服务器上的文件夹大小，Outlook 会打开存储上的文件夹与[IMsgStore::OpenEntry](imsgstore-openentry.md)，传递标志**MAPI_NO_CACHE**，，然后它查询的**PR_MESSAGE_SIZE_EXTENDED**。</span><span class="sxs-lookup"><span data-stu-id="c2c27-132">To query for the folder size on the server, Outlook opens a folder on the store with [IMsgStore::OpenEntry](imsgstore-openentry.md), passing the flag **MAPI_NO_CACHE**, and then it queries for **PR_MESSAGE_SIZE_EXTENDED**.</span></span> <span data-ttu-id="c2c27-133">存储提供程序然后返回服务器上的文件夹大小。</span><span class="sxs-lookup"><span data-stu-id="c2c27-133">The store provider should then return the folder size on the server.</span></span>
  
<span data-ttu-id="c2c27-134">要查询的本地驱动器上的文件夹的大小，Outlook 将打开如果没有**MAPI_NO_CACHE**标志文件夹。</span><span class="sxs-lookup"><span data-stu-id="c2c27-134">To query for the size of a folder on the local drive, Outlook opens the folder without the **MAPI_NO_CACHE** flag.</span></span> <span data-ttu-id="c2c27-135">然后它**PR_MESSAGE_SIZE_EXTENDED**; 查询存储提供程序应在本地驱动器返回指定的文件夹的大小。</span><span class="sxs-lookup"><span data-stu-id="c2c27-135">It then queries for **PR_MESSAGE_SIZE_EXTENDED**; the store provider should return the size of the specified folder on the local drive.</span></span>
  
<span data-ttu-id="c2c27-136">设置此属性，将同步到服务器的存储内容的存储提供程序可以显示 Outlook**文件夹大小**对话框中的服务器上的文件夹大小数据。</span><span class="sxs-lookup"><span data-stu-id="c2c27-136">With this property set, store providers that synchronize store contents to a server can display folder size data on the server in the Outlook **Folder Size** dialog box.</span></span> <span data-ttu-id="c2c27-137">用户可以进行比较，与服务器配额其当前服务器存储使用情况。</span><span class="sxs-lookup"><span data-stu-id="c2c27-137">Users can then compare their current server storage usage with server quotas.</span></span> 
  

