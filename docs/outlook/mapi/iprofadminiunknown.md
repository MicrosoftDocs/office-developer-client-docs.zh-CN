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
ms.openlocfilehash: cbdfba68490b1e756f277c6e552235368a86f310
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33434114"
---
# <a name="iprofadmin--iunknown"></a><span data-ttu-id="34920-103">IProfAdmin : IUnknown</span><span class="sxs-lookup"><span data-stu-id="34920-103">IProfAdmin : IUnknown</span></span>

  
  
<span data-ttu-id="34920-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="34920-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="34920-105">支持配置文件的管理。</span><span class="sxs-lookup"><span data-stu-id="34920-105">Supports the administration of profiles.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="34920-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="34920-106">Header file:</span></span>  <br/> |<span data-ttu-id="34920-107">Mapix</span><span class="sxs-lookup"><span data-stu-id="34920-107">Mapix.h</span></span>  <br/> |
|<span data-ttu-id="34920-108">公开者:</span><span class="sxs-lookup"><span data-stu-id="34920-108">Exposed by:</span></span>  <br/> |<span data-ttu-id="34920-109">Profile administration 对象</span><span class="sxs-lookup"><span data-stu-id="34920-109">Profile administration object</span></span>  <br/> |
|<span data-ttu-id="34920-110">实现者：</span><span class="sxs-lookup"><span data-stu-id="34920-110">Implemented by:</span></span>  <br/> |<span data-ttu-id="34920-111">MAPI</span><span class="sxs-lookup"><span data-stu-id="34920-111">MAPI</span></span>  <br/> |
|<span data-ttu-id="34920-112">调用者：</span><span class="sxs-lookup"><span data-stu-id="34920-112">Called by:</span></span>  <br/> |<span data-ttu-id="34920-113">客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="34920-113">Client applications</span></span>  <br/> |
|<span data-ttu-id="34920-114">接口标识符:</span><span class="sxs-lookup"><span data-stu-id="34920-114">Interface identifier:</span></span>  <br/> |<span data-ttu-id="34920-115">IID_IProfAdmin</span><span class="sxs-lookup"><span data-stu-id="34920-115">IID_IProfAdmin</span></span>  <br/> |
|<span data-ttu-id="34920-116">指针类型:</span><span class="sxs-lookup"><span data-stu-id="34920-116">Pointer type:</span></span>  <br/> |<span data-ttu-id="34920-117">LPPROFADMIN</span><span class="sxs-lookup"><span data-stu-id="34920-117">LPPROFADMIN</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="34920-118">Vtable 顺序</span><span class="sxs-lookup"><span data-stu-id="34920-118">Vtable order</span></span>

|||
|:-----|:-----|
|[<span data-ttu-id="34920-119">GetLastError</span><span class="sxs-lookup"><span data-stu-id="34920-119">GetLastError</span></span>](iprofadmin-getlasterror.md) <br/> |<span data-ttu-id="34920-120">返回一个[MAPIERROR](mapierror.md)结构, 该结构包含有关配置文件管理对象中发生的上一个错误的信息。</span><span class="sxs-lookup"><span data-stu-id="34920-120">Returns a [MAPIERROR](mapierror.md) structure that contains information about the previous error that occurred to a profile administration object.</span></span>  <br/> |
|[<span data-ttu-id="34920-121">GetProfileTable</span><span class="sxs-lookup"><span data-stu-id="34920-121">GetProfileTable</span></span>](iprofadmin-getprofiletable.md) <br/> |<span data-ttu-id="34920-122">提供对配置文件表 (包含所有可用配置文件的相关信息的表) 的访问权限。</span><span class="sxs-lookup"><span data-stu-id="34920-122">Provides access to the profile table, a table that contains information about all of the available profiles.</span></span>  <br/> |
|[<span data-ttu-id="34920-123">CreateProfile</span><span class="sxs-lookup"><span data-stu-id="34920-123">CreateProfile</span></span>](iprofadmin-createprofile.md) <br/> |<span data-ttu-id="34920-124">创建新的配置文件。</span><span class="sxs-lookup"><span data-stu-id="34920-124">Creates a new profile.</span></span>  <br/> |
|[<span data-ttu-id="34920-125">DeleteProfile</span><span class="sxs-lookup"><span data-stu-id="34920-125">DeleteProfile</span></span>](iprofadmin-deleteprofile.md) <br/> |<span data-ttu-id="34920-126">删除配置文件。</span><span class="sxs-lookup"><span data-stu-id="34920-126">Deletes a profile.</span></span>  <br/> |
|[<span data-ttu-id="34920-127">ChangeProfilePassword</span><span class="sxs-lookup"><span data-stu-id="34920-127">ChangeProfilePassword</span></span>](iprofadmin-changeprofilepassword.md) <br/> |<span data-ttu-id="34920-128">已弃用。</span><span class="sxs-lookup"><span data-stu-id="34920-128">Deprecated.</span></span> <span data-ttu-id="34920-129">更改配置文件的密码。</span><span class="sxs-lookup"><span data-stu-id="34920-129">Changes the password for a profile.</span></span>  <br/> |
|[<span data-ttu-id="34920-130">CopyProfile</span><span class="sxs-lookup"><span data-stu-id="34920-130">CopyProfile</span></span>](iprofadmin-copyprofile.md) <br/> |<span data-ttu-id="34920-131">复制配置文件。</span><span class="sxs-lookup"><span data-stu-id="34920-131">Copies a profile.</span></span>  <br/> |
|[<span data-ttu-id="34920-132">RenameProfile</span><span class="sxs-lookup"><span data-stu-id="34920-132">RenameProfile</span></span>](iprofadmin-renameprofile.md) <br/> |<span data-ttu-id="34920-133">为配置文件分配一个新名称。</span><span class="sxs-lookup"><span data-stu-id="34920-133">Assigns a new name to a profile.</span></span>  <br/> |
|[<span data-ttu-id="34920-134">SetDefaultProfile</span><span class="sxs-lookup"><span data-stu-id="34920-134">SetDefaultProfile</span></span>](iprofadmin-setdefaultprofile.md) <br/> |<span data-ttu-id="34920-135">设置或清除客户端的默认配置文件。</span><span class="sxs-lookup"><span data-stu-id="34920-135">Sets or clears a client's default profile.</span></span>  <br/> |
|[<span data-ttu-id="34920-136">AdminServices</span><span class="sxs-lookup"><span data-stu-id="34920-136">AdminServices</span></span>](iprofadmin-adminservices.md) <br/> |<span data-ttu-id="34920-137">提供对邮件服务管理对象的访问权限, 以对配置文件中的邮件服务进行更改。</span><span class="sxs-lookup"><span data-stu-id="34920-137">Provides access to a message service administration object for making changes to the message services in a profile.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="34920-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="34920-138">See also</span></span>



[<span data-ttu-id="34920-139">MAPI 接口</span><span class="sxs-lookup"><span data-stu-id="34920-139">MAPI Interfaces</span></span>](mapi-interfaces.md)

