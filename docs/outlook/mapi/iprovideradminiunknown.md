---
title: IProviderAdmin IUnknown
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IProviderAdmin
api_type:
- COM
ms.assetid: bdb4cdca-8dfd-4f90-9467-ec31cea3f518
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 41195a49d1bf3566c81fe6e97697012209cbc5ac
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776022"
---
# <a name="iprovideradmin--iunknown"></a><span data-ttu-id="58ef4-103">IProviderAdmin: IUnknown</span><span class="sxs-lookup"><span data-stu-id="58ef4-103">IProviderAdmin : IUnknown</span></span>

  
  
<span data-ttu-id="58ef4-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="58ef4-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="58ef4-105">适用于邮件服务中的服务提供商。</span><span class="sxs-lookup"><span data-stu-id="58ef4-105">Works with service providers in a message service.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="58ef4-106">头文件：</span><span class="sxs-lookup"><span data-stu-id="58ef4-106">Header file:</span></span>  <br/> |<span data-ttu-id="58ef4-107">Mapidefs.h</span><span class="sxs-lookup"><span data-stu-id="58ef4-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="58ef4-108">由公开：</span><span class="sxs-lookup"><span data-stu-id="58ef4-108">Exposed by:</span></span>  <br/> |<span data-ttu-id="58ef4-109">提供程序管理对象</span><span class="sxs-lookup"><span data-stu-id="58ef4-109">Provider administration objects</span></span>  <br/> |
|<span data-ttu-id="58ef4-110">通过实现：</span><span class="sxs-lookup"><span data-stu-id="58ef4-110">Implemented by:</span></span>  <br/> |<span data-ttu-id="58ef4-111">MAPI</span><span class="sxs-lookup"><span data-stu-id="58ef4-111">MAPI</span></span>  <br/> |
|<span data-ttu-id="58ef4-112">调用：</span><span class="sxs-lookup"><span data-stu-id="58ef4-112">Called by:</span></span>  <br/> |<span data-ttu-id="58ef4-113">客户端应用程序和服务提供商</span><span class="sxs-lookup"><span data-stu-id="58ef4-113">Client applications and service providers</span></span>  <br/> |
|<span data-ttu-id="58ef4-114">接口标识符：</span><span class="sxs-lookup"><span data-stu-id="58ef4-114">Interface identifier:</span></span>  <br/> |<span data-ttu-id="58ef4-115">IID_IProviderAdmin</span><span class="sxs-lookup"><span data-stu-id="58ef4-115">IID_IProviderAdmin</span></span>  <br/> |
|<span data-ttu-id="58ef4-116">指针类型：</span><span class="sxs-lookup"><span data-stu-id="58ef4-116">Pointer type:</span></span>  <br/> |<span data-ttu-id="58ef4-117">LPPROVIDERADMIN</span><span class="sxs-lookup"><span data-stu-id="58ef4-117">LPPROVIDERADMIN</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="58ef4-118">Vtable 顺序排列</span><span class="sxs-lookup"><span data-stu-id="58ef4-118">Vtable order</span></span>

|||
|:-----|:-----|
|[<span data-ttu-id="58ef4-119">时出错</span><span class="sxs-lookup"><span data-stu-id="58ef4-119">GetLastError</span></span>](iprovideradmin-getlasterror.md) <br/> |<span data-ttu-id="58ef4-120">返回一个[MAPIERROR](mapierror.md)结构，其中包含有关前面的提供程序的管理对象发生的错误的信息。</span><span class="sxs-lookup"><span data-stu-id="58ef4-120">Returns a [MAPIERROR](mapierror.md) structure that contains information about the previous error that occurred to the provider administration object.</span></span>  <br/> |
|[<span data-ttu-id="58ef4-121">GetProviderTable</span><span class="sxs-lookup"><span data-stu-id="58ef4-121">GetProviderTable</span></span>](iprovideradmin-getprovidertable.md) <br/> |<span data-ttu-id="58ef4-122">提供对邮件服务提供程序表中，消息服务的服务提供商的列表的访问。</span><span class="sxs-lookup"><span data-stu-id="58ef4-122">Provides access to the message service's provider table, a list of the service providers in the message service.</span></span>  <br/> |
|[<span data-ttu-id="58ef4-123">CreateProvider</span><span class="sxs-lookup"><span data-stu-id="58ef4-123">CreateProvider</span></span>](iprovideradmin-createprovider.md) <br/> |<span data-ttu-id="58ef4-124">向消息服务的服务提供商。</span><span class="sxs-lookup"><span data-stu-id="58ef4-124">Adds a service provider to the message service.</span></span>  <br/> |
|[<span data-ttu-id="58ef4-125">DeleteProvider</span><span class="sxs-lookup"><span data-stu-id="58ef4-125">DeleteProvider</span></span>](iprovideradmin-deleteprovider.md) <br/> |<span data-ttu-id="58ef4-126">删除消息服务的服务提供商。</span><span class="sxs-lookup"><span data-stu-id="58ef4-126">Deletes a service provider from the message service.</span></span>  <br/> |
|[<span data-ttu-id="58ef4-127">OpenProfileSection</span><span class="sxs-lookup"><span data-stu-id="58ef4-127">OpenProfileSection</span></span>](iprovideradmin-openprofilesection.md) <br/> |<span data-ttu-id="58ef4-128">从当前配置文件中打开配置文件一节并返回进一步访问[IProfSect](iprofsectimapiprop.md)指针。</span><span class="sxs-lookup"><span data-stu-id="58ef4-128">Opens a profile section from the current profile and returns an [IProfSect](iprofsectimapiprop.md) pointer for further access.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="58ef4-129">备注</span><span class="sxs-lookup"><span data-stu-id="58ef4-129">Remarks</span></span>

<span data-ttu-id="58ef4-130">客户端可以通过调用[IMsgServiceAdmin::AdminProviders](imsgserviceadmin-adminproviders.md)方法; **IProviderAdmin**界面得到指针服务提供商其消息服务的入口点函数调用时传递**IProviderAdmin**指针。</span><span class="sxs-lookup"><span data-stu-id="58ef4-130">Clients can get a pointer to an **IProviderAdmin** interface by calling the [IMsgServiceAdmin::AdminProviders](imsgserviceadmin-adminproviders.md) method; service providers are passed an **IProviderAdmin** pointer when their message service's entry point function is called.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="58ef4-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="58ef4-131">See also</span></span>



[<span data-ttu-id="58ef4-132">MAPI 接口</span><span class="sxs-lookup"><span data-stu-id="58ef4-132">MAPI Interfaces</span></span>](mapi-interfaces.md)

