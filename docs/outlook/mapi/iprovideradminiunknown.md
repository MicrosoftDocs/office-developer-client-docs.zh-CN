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
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: bedec72e8371d0e8aa69415d2f0dc77b4c62ff76
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33437530"
---
# <a name="iprovideradmin--iunknown"></a><span data-ttu-id="1c3a5-103">IProviderAdmin : IUnknown</span><span class="sxs-lookup"><span data-stu-id="1c3a5-103">IProviderAdmin : IUnknown</span></span>

  
  
<span data-ttu-id="1c3a5-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="1c3a5-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="1c3a5-105">在邮件服务中处理服务提供程序。</span><span class="sxs-lookup"><span data-stu-id="1c3a5-105">Works with service providers in a message service.</span></span> 
  
|||
|:-----|:-----|
|<span data-ttu-id="1c3a5-106">标头文件：</span><span class="sxs-lookup"><span data-stu-id="1c3a5-106">Header file:</span></span>  <br/> |<span data-ttu-id="1c3a5-107">mapidefs。h</span><span class="sxs-lookup"><span data-stu-id="1c3a5-107">Mapidefs.h</span></span>  <br/> |
|<span data-ttu-id="1c3a5-108">公开者:</span><span class="sxs-lookup"><span data-stu-id="1c3a5-108">Exposed by:</span></span>  <br/> |<span data-ttu-id="1c3a5-109">提供程序管理对象</span><span class="sxs-lookup"><span data-stu-id="1c3a5-109">Provider administration objects</span></span>  <br/> |
|<span data-ttu-id="1c3a5-110">实现者：</span><span class="sxs-lookup"><span data-stu-id="1c3a5-110">Implemented by:</span></span>  <br/> |<span data-ttu-id="1c3a5-111">MAPI</span><span class="sxs-lookup"><span data-stu-id="1c3a5-111">MAPI</span></span>  <br/> |
|<span data-ttu-id="1c3a5-112">调用者：</span><span class="sxs-lookup"><span data-stu-id="1c3a5-112">Called by:</span></span>  <br/> |<span data-ttu-id="1c3a5-113">客户端应用程序和服务提供程序</span><span class="sxs-lookup"><span data-stu-id="1c3a5-113">Client applications and service providers</span></span>  <br/> |
|<span data-ttu-id="1c3a5-114">接口标识符:</span><span class="sxs-lookup"><span data-stu-id="1c3a5-114">Interface identifier:</span></span>  <br/> |<span data-ttu-id="1c3a5-115">IID_IProviderAdmin</span><span class="sxs-lookup"><span data-stu-id="1c3a5-115">IID_IProviderAdmin</span></span>  <br/> |
|<span data-ttu-id="1c3a5-116">指针类型:</span><span class="sxs-lookup"><span data-stu-id="1c3a5-116">Pointer type:</span></span>  <br/> |<span data-ttu-id="1c3a5-117">LPPROVIDERADMIN</span><span class="sxs-lookup"><span data-stu-id="1c3a5-117">LPPROVIDERADMIN</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="1c3a5-118">Vtable 顺序</span><span class="sxs-lookup"><span data-stu-id="1c3a5-118">Vtable order</span></span>

|||
|:-----|:-----|
|[<span data-ttu-id="1c3a5-119">GetLastError</span><span class="sxs-lookup"><span data-stu-id="1c3a5-119">GetLastError</span></span>](iprovideradmin-getlasterror.md) <br/> |<span data-ttu-id="1c3a5-120">返回一个[MAPIERROR](mapierror.md)结构, 该结构包含有关提供程序管理对象发生的上一个错误的信息。</span><span class="sxs-lookup"><span data-stu-id="1c3a5-120">Returns a [MAPIERROR](mapierror.md) structure that contains information about the previous error that occurred to the provider administration object.</span></span>  <br/> |
|[<span data-ttu-id="1c3a5-121">GetProviderTable</span><span class="sxs-lookup"><span data-stu-id="1c3a5-121">GetProviderTable</span></span>](iprovideradmin-getprovidertable.md) <br/> |<span data-ttu-id="1c3a5-122">提供对邮件服务的提供程序表的访问权限 (邮件服务中的服务提供程序的列表)。</span><span class="sxs-lookup"><span data-stu-id="1c3a5-122">Provides access to the message service's provider table, a list of the service providers in the message service.</span></span>  <br/> |
|[<span data-ttu-id="1c3a5-123">CreateProvider</span><span class="sxs-lookup"><span data-stu-id="1c3a5-123">CreateProvider</span></span>](iprovideradmin-createprovider.md) <br/> |<span data-ttu-id="1c3a5-124">向邮件服务中添加服务提供程序。</span><span class="sxs-lookup"><span data-stu-id="1c3a5-124">Adds a service provider to the message service.</span></span>  <br/> |
|[<span data-ttu-id="1c3a5-125">DeleteProvider</span><span class="sxs-lookup"><span data-stu-id="1c3a5-125">DeleteProvider</span></span>](iprovideradmin-deleteprovider.md) <br/> |<span data-ttu-id="1c3a5-126">从邮件服务中删除服务提供程序。</span><span class="sxs-lookup"><span data-stu-id="1c3a5-126">Deletes a service provider from the message service.</span></span>  <br/> |
|[<span data-ttu-id="1c3a5-127">OpenProfileSection</span><span class="sxs-lookup"><span data-stu-id="1c3a5-127">OpenProfileSection</span></span>](iprovideradmin-openprofilesection.md) <br/> |<span data-ttu-id="1c3a5-128">从当前配置文件打开一个配置文件部分, 并返回一个[IProfSect](iprofsectimapiprop.md)指针以供进一步访问。</span><span class="sxs-lookup"><span data-stu-id="1c3a5-128">Opens a profile section from the current profile and returns an [IProfSect](iprofsectimapiprop.md) pointer for further access.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="1c3a5-129">说明</span><span class="sxs-lookup"><span data-stu-id="1c3a5-129">Remarks</span></span>

<span data-ttu-id="1c3a5-130">客户端可以通过调用[IMsgServiceAdmin:: AdminProviders](imsgserviceadmin-adminproviders.md)方法获取指向**IProviderAdmin**接口的指针;调用服务提供程序的消息服务入口点函数时, 会向其传递**IProviderAdmin**指针。</span><span class="sxs-lookup"><span data-stu-id="1c3a5-130">Clients can get a pointer to an **IProviderAdmin** interface by calling the [IMsgServiceAdmin::AdminProviders](imsgserviceadmin-adminproviders.md) method; service providers are passed an **IProviderAdmin** pointer when their message service's entry point function is called.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="1c3a5-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1c3a5-131">See also</span></span>



[<span data-ttu-id="1c3a5-132">MAPI 接口</span><span class="sxs-lookup"><span data-stu-id="1c3a5-132">MAPI Interfaces</span></span>](mapi-interfaces.md)

