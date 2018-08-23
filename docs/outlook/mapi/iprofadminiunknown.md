---
title: IProfAdmin IUnknown
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IProfAdmin
api_type:
- COM
ms.assetid: 274899cc-2894-4d99-84ec-f18121e856a0
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 28dd45f29610b7ad56b4d3302715311569d497c4
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22577413"
---
# <a name="iprofadmin--iunknown"></a><span data-ttu-id="32a64-103">IProfAdmin : IUnknown</span><span class="sxs-lookup"><span data-stu-id="32a64-103">IProfAdmin : IUnknown</span></span>

  
  
<span data-ttu-id="32a64-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="32a64-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="32a64-105">支持配置文件的管理。</span><span class="sxs-lookup"><span data-stu-id="32a64-105">Supports the administration of profiles.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="32a64-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="32a64-106">Header file:</span></span>  <br/> |<span data-ttu-id="32a64-107">Mapix.h</span><span class="sxs-lookup"><span data-stu-id="32a64-107">Mapix.h</span></span>  <br/> |
|<span data-ttu-id="32a64-108">由公开：</span><span class="sxs-lookup"><span data-stu-id="32a64-108">Exposed by:</span></span>  <br/> |<span data-ttu-id="32a64-109">配置文件管理对象</span><span class="sxs-lookup"><span data-stu-id="32a64-109">Profile administration object</span></span>  <br/> |
|<span data-ttu-id="32a64-110">通过实现：</span><span class="sxs-lookup"><span data-stu-id="32a64-110">Implemented by:</span></span>  <br/> |<span data-ttu-id="32a64-111">MAPI</span><span class="sxs-lookup"><span data-stu-id="32a64-111">MAPI</span></span>  <br/> |
|<span data-ttu-id="32a64-112">调用：</span><span class="sxs-lookup"><span data-stu-id="32a64-112">Called by:</span></span>  <br/> |<span data-ttu-id="32a64-113">客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="32a64-113">Client applications</span></span>  <br/> |
|<span data-ttu-id="32a64-114">接口标识符：</span><span class="sxs-lookup"><span data-stu-id="32a64-114">Interface identifier:</span></span>  <br/> |<span data-ttu-id="32a64-115">IID_IProfAdmin</span><span class="sxs-lookup"><span data-stu-id="32a64-115">IID_IProfAdmin</span></span>  <br/> |
|<span data-ttu-id="32a64-116">指针类型：</span><span class="sxs-lookup"><span data-stu-id="32a64-116">Pointer type:</span></span>  <br/> |<span data-ttu-id="32a64-117">LPPROFADMIN</span><span class="sxs-lookup"><span data-stu-id="32a64-117">LPPROFADMIN</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="32a64-118">Vtable 顺序排列</span><span class="sxs-lookup"><span data-stu-id="32a64-118">Vtable order</span></span>

|||
|:-----|:-----|
|[<span data-ttu-id="32a64-119">时出错</span><span class="sxs-lookup"><span data-stu-id="32a64-119">GetLastError</span></span>](iprofadmin-getlasterror.md) <br/> |<span data-ttu-id="32a64-120">返回一个[MAPIERROR](mapierror.md)结构，其中包含有关前面的配置文件管理对象发生的错误的信息。</span><span class="sxs-lookup"><span data-stu-id="32a64-120">Returns a [MAPIERROR](mapierror.md) structure that contains information about the previous error that occurred to a profile administration object.</span></span>  <br/> |
|[<span data-ttu-id="32a64-121">GetProfileTable</span><span class="sxs-lookup"><span data-stu-id="32a64-121">GetProfileTable</span></span>](iprofadmin-getprofiletable.md) <br/> |<span data-ttu-id="32a64-122">提供对配置文件表中，一个表，包含有关所有可用的配置文件信息的访问。</span><span class="sxs-lookup"><span data-stu-id="32a64-122">Provides access to the profile table, a table that contains information about all of the available profiles.</span></span>  <br/> |
|[<span data-ttu-id="32a64-123">CreateProfile</span><span class="sxs-lookup"><span data-stu-id="32a64-123">CreateProfile</span></span>](iprofadmin-createprofile.md) <br/> |<span data-ttu-id="32a64-124">创建新的配置文件。</span><span class="sxs-lookup"><span data-stu-id="32a64-124">Creates a new profile.</span></span>  <br/> |
|[<span data-ttu-id="32a64-125">DeleteProfile</span><span class="sxs-lookup"><span data-stu-id="32a64-125">DeleteProfile</span></span>](iprofadmin-deleteprofile.md) <br/> |<span data-ttu-id="32a64-126">删除配置文件。</span><span class="sxs-lookup"><span data-stu-id="32a64-126">Deletes a profile.</span></span>  <br/> |
|[<span data-ttu-id="32a64-127">ChangeProfilePassword</span><span class="sxs-lookup"><span data-stu-id="32a64-127">ChangeProfilePassword</span></span>](iprofadmin-changeprofilepassword.md) <br/> |<span data-ttu-id="32a64-128">已弃用。</span><span class="sxs-lookup"><span data-stu-id="32a64-128">Deprecated.</span></span> <span data-ttu-id="32a64-129">更改配置文件的密码。</span><span class="sxs-lookup"><span data-stu-id="32a64-129">Changes the password for a profile.</span></span>  <br/> |
|[<span data-ttu-id="32a64-130">CopyProfile</span><span class="sxs-lookup"><span data-stu-id="32a64-130">CopyProfile</span></span>](iprofadmin-copyprofile.md) <br/> |<span data-ttu-id="32a64-131">一个配置文件的副本。</span><span class="sxs-lookup"><span data-stu-id="32a64-131">Copies a profile.</span></span>  <br/> |
|[<span data-ttu-id="32a64-132">RenameProfile</span><span class="sxs-lookup"><span data-stu-id="32a64-132">RenameProfile</span></span>](iprofadmin-renameprofile.md) <br/> |<span data-ttu-id="32a64-133">向一个配置文件分配一个新名称。</span><span class="sxs-lookup"><span data-stu-id="32a64-133">Assigns a new name to a profile.</span></span>  <br/> |
|[<span data-ttu-id="32a64-134">SetDefaultProfile</span><span class="sxs-lookup"><span data-stu-id="32a64-134">SetDefaultProfile</span></span>](iprofadmin-setdefaultprofile.md) <br/> |<span data-ttu-id="32a64-135">设置或清除客户端的默认配置文件。</span><span class="sxs-lookup"><span data-stu-id="32a64-135">Sets or clears a client's default profile.</span></span>  <br/> |
|[<span data-ttu-id="32a64-136">AdminServices</span><span class="sxs-lookup"><span data-stu-id="32a64-136">AdminServices</span></span>](iprofadmin-adminservices.md) <br/> |<span data-ttu-id="32a64-137">提供对邮件服务管理对象的更改配置文件中的消息服务的访问。</span><span class="sxs-lookup"><span data-stu-id="32a64-137">Provides access to a message service administration object for making changes to the message services in a profile.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="32a64-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="32a64-138">See also</span></span>



[<span data-ttu-id="32a64-139">MAPI 接口</span><span class="sxs-lookup"><span data-stu-id="32a64-139">MAPI Interfaces</span></span>](mapi-interfaces.md)

