---
title: IMAPIOffline IUnknown
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIOffline
api_type:
- COM
ms.assetid: 211281ff-3c22-1b51-4b72-ca1e313c7202
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 616bb4774e2ca5385e7da867477cb8849d94336b
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22568383"
---
# <a name="imapioffline--iunknown"></a><span data-ttu-id="dd865-103">IMAPIOffline : IUnknown</span><span class="sxs-lookup"><span data-stu-id="dd865-103">IMAPIOffline : IUnknown</span></span>

  
  
<span data-ttu-id="dd865-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="dd865-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="dd865-105">提供脱机对象的信息。</span><span class="sxs-lookup"><span data-stu-id="dd865-105">Provides information for an offline object.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="dd865-106">提供者：</span><span class="sxs-lookup"><span data-stu-id="dd865-106">Provided by:</span></span>  <br/> |<span data-ttu-id="dd865-107">[IMAPIOfflineMgr](imapiofflinemgrimapioffline.md)查询</span><span class="sxs-lookup"><span data-stu-id="dd865-107">Query on [IMAPIOfflineMgr](imapiofflinemgrimapioffline.md)</span></span> <br/> |
|<span data-ttu-id="dd865-108">调用：</span><span class="sxs-lookup"><span data-stu-id="dd865-108">Called by:</span></span>  <br/> |<span data-ttu-id="dd865-109">客户端</span><span class="sxs-lookup"><span data-stu-id="dd865-109">Client</span></span>  <br/> |
|<span data-ttu-id="dd865-110">接口标识符：</span><span class="sxs-lookup"><span data-stu-id="dd865-110">Interface identifier:</span></span>  <br/> |<span data-ttu-id="dd865-111">IID_IMAPIOffline</span><span class="sxs-lookup"><span data-stu-id="dd865-111">IID_IMAPIOffline</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="dd865-112">Vtable 顺序排列</span><span class="sxs-lookup"><span data-stu-id="dd865-112">Vtable order</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="dd865-113">**[SetCurrentState](imapioffline-setcurrentstate.md)**</span><span class="sxs-lookup"><span data-stu-id="dd865-113">**[SetCurrentState](imapioffline-setcurrentstate.md)**</span></span> <br/> |<span data-ttu-id="dd865-114">设置为联机或脱机脱机对象的当前状态。</span><span class="sxs-lookup"><span data-stu-id="dd865-114">Sets the current state of an offline object to online or offline.</span></span>  <br/> |
|<span data-ttu-id="dd865-115">**[GetCapabilities](imapioffline-getcapabilities.md)**</span><span class="sxs-lookup"><span data-stu-id="dd865-115">**[GetCapabilities](imapioffline-getcapabilities.md)**</span></span> <br/> |<span data-ttu-id="dd865-116">获取为其脱机对象支持回调的条件。</span><span class="sxs-lookup"><span data-stu-id="dd865-116">Gets the conditions for which callbacks are supported by an offline object.</span></span>  <br/> |
|<span data-ttu-id="dd865-117">**[GetCurrentState](imapioffline-getcurrentstate.md)**</span><span class="sxs-lookup"><span data-stu-id="dd865-117">**[GetCurrentState](imapioffline-getcurrentstate.md)**</span></span> <br/> |<span data-ttu-id="dd865-118">获取一个脱机对象的当前联机或脱机状态。</span><span class="sxs-lookup"><span data-stu-id="dd865-118">Gets the current online or offline state of an offline object.</span></span>  <br/> |
| <span data-ttu-id="dd865-119">*占位符成员*</span><span class="sxs-lookup"><span data-stu-id="dd865-119">*Placeholder member*</span></span>  <br/> |<span data-ttu-id="dd865-120">此成员是一个占位符，不支持。</span><span class="sxs-lookup"><span data-stu-id="dd865-120">This member is a placeholder and is not supported.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="dd865-121">注解</span><span class="sxs-lookup"><span data-stu-id="dd865-121">Remarks</span></span>

<span data-ttu-id="dd865-122">客户端使用**[HrOpenOfflineObj](hropenofflineobj.md)** 打开并获取支持**IMAPIOfflineMgr**脱机对象。</span><span class="sxs-lookup"><span data-stu-id="dd865-122">A client uses **[HrOpenOfflineObj](hropenofflineobj.md)** to open and obtain an offline object that supports **IMAPIOfflineMgr**.</span></span> <span data-ttu-id="dd865-123">由于**IMAPIOfflineMgr**继承从[iunknown 导出](http://msdn.microsoft.com/en-us/library/ms680509%28v=VS.85%29.aspx)，客户端可以此接口查询 （通过使用[IUnknown::QueryInterface](http://msdn.microsoft.com/en-us/library/ms682521%28v=VS.85%29.aspx)） 来获取**IMAPIOffline**脱机对象指向的接口指针的指针。</span><span class="sxs-lookup"><span data-stu-id="dd865-123">Because **IMAPIOfflineMgr** inherits from [IUnknown](http://msdn.microsoft.com/en-us/library/ms680509%28v=VS.85%29.aspx), the client can query this interface (by using [IUnknown::QueryInterface](http://msdn.microsoft.com/en-us/library/ms682521%28v=VS.85%29.aspx)) to obtain a pointer to the interface pointer for **IMAPIOffline** for the offline object.</span></span> <span data-ttu-id="dd865-124">客户端然后可以获取或设置对象的当前状态或找出有关对象的回调功能 （通过调用**IMAPIOffline::GetCapabilities** ） 并选择使用**[IMAPIOfflineMgr](imapiofflinemgrimapioffline.md)** 设置回调。</span><span class="sxs-lookup"><span data-stu-id="dd865-124">The client can then get or set the current state of the object, or find out about the callback capabilities of the object (by calling **IMAPIOffline::GetCapabilities** ) and choose to set up callbacks by using **[IMAPIOfflineMgr](imapiofflinemgrimapioffline.md)**.</span></span> 
  
<span data-ttu-id="dd865-125">此接口中的成员保留供内部使用的 Microsoft Outlook 2013 的占位符并可能会更改。</span><span class="sxs-lookup"><span data-stu-id="dd865-125">A member in this interface is a placeholder reserved for the internal use of Microsoft Outlook 2013 and is subject to change.</span></span> <span data-ttu-id="dd865-126">必须只记录使用此接口中的其他成员。</span><span class="sxs-lookup"><span data-stu-id="dd865-126">Other members in this interface must be used only as documented.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="dd865-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dd865-127">See also</span></span>



[<span data-ttu-id="dd865-128">IMAPIOfflineMgr : IMAPIOffline</span><span class="sxs-lookup"><span data-stu-id="dd865-128">IMAPIOfflineMgr : IMAPIOffline</span></span>](imapiofflinemgrimapioffline.md)


[<span data-ttu-id="dd865-129">关于脱机状态 API</span><span class="sxs-lookup"><span data-stu-id="dd865-129">About the Offline State API</span></span>](about-the-offline-state-api.md)
  
[<span data-ttu-id="dd865-130">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="dd865-130">MAPI Constants</span></span>](mapi-constants.md)
  
[<span data-ttu-id="dd865-131">MAPI 接口</span><span class="sxs-lookup"><span data-stu-id="dd865-131">MAPI Interfaces</span></span>](mapi-interfaces.md)

