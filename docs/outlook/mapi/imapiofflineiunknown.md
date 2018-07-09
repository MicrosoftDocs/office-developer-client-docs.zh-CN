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
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 6f17e501a90a50a4984cae470d3924205c78a604
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775506"
---
# <a name="imapioffline--iunknown"></a><span data-ttu-id="8d119-103">IMAPIOffline: IUnknown</span><span class="sxs-lookup"><span data-stu-id="8d119-103">IMAPIOffline : IUnknown</span></span>

  
  
<span data-ttu-id="8d119-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="8d119-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="8d119-105">提供脱机对象的信息。</span><span class="sxs-lookup"><span data-stu-id="8d119-105">Provides information for an offline object.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="8d119-106">提供者：</span><span class="sxs-lookup"><span data-stu-id="8d119-106">Provided by:</span></span>  <br/> |<span data-ttu-id="8d119-107">[IMAPIOfflineMgr](imapiofflinemgrimapioffline.md)查询</span><span class="sxs-lookup"><span data-stu-id="8d119-107">Query on [IMAPIOfflineMgr](imapiofflinemgrimapioffline.md)</span></span> <br/> |
|<span data-ttu-id="8d119-108">调用：</span><span class="sxs-lookup"><span data-stu-id="8d119-108">Called by:</span></span>  <br/> |<span data-ttu-id="8d119-109">客户端</span><span class="sxs-lookup"><span data-stu-id="8d119-109">Client</span></span>  <br/> |
|<span data-ttu-id="8d119-110">接口标识符：</span><span class="sxs-lookup"><span data-stu-id="8d119-110">Interface identifier:</span></span>  <br/> |<span data-ttu-id="8d119-111">IID_IMAPIOffline</span><span class="sxs-lookup"><span data-stu-id="8d119-111">IID_IMAPIOffline</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="8d119-112">Vtable 顺序排列</span><span class="sxs-lookup"><span data-stu-id="8d119-112">Vtable order</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="8d119-113">**[SetCurrentState](imapioffline-setcurrentstate.md)**</span><span class="sxs-lookup"><span data-stu-id="8d119-113">**[SetCurrentState](imapioffline-setcurrentstate.md)**</span></span> <br/> |<span data-ttu-id="8d119-114">设置为联机或脱机脱机对象的当前状态。</span><span class="sxs-lookup"><span data-stu-id="8d119-114">Sets the current state of an offline object to online or offline.</span></span>  <br/> |
|<span data-ttu-id="8d119-115">**[GetCapabilities](imapioffline-getcapabilities.md)**</span><span class="sxs-lookup"><span data-stu-id="8d119-115">**[GetCapabilities](imapioffline-getcapabilities.md)**</span></span> <br/> |<span data-ttu-id="8d119-116">获取为其脱机对象支持回调的条件。</span><span class="sxs-lookup"><span data-stu-id="8d119-116">Gets the conditions for which callbacks are supported by an offline object.</span></span>  <br/> |
|<span data-ttu-id="8d119-117">**[GetCurrentState](imapioffline-getcurrentstate.md)**</span><span class="sxs-lookup"><span data-stu-id="8d119-117">**[GetCurrentState](imapioffline-getcurrentstate.md)**</span></span> <br/> |<span data-ttu-id="8d119-118">获取一个脱机对象的当前联机或脱机状态。</span><span class="sxs-lookup"><span data-stu-id="8d119-118">Gets the current online or offline state of an offline object.</span></span>  <br/> |
| <span data-ttu-id="8d119-119">*占位符成员*</span><span class="sxs-lookup"><span data-stu-id="8d119-119">*Placeholder member*</span></span>  <br/> |<span data-ttu-id="8d119-120">此成员是一个占位符，不支持。</span><span class="sxs-lookup"><span data-stu-id="8d119-120">This member is a placeholder and is not supported.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="8d119-121">备注</span><span class="sxs-lookup"><span data-stu-id="8d119-121">Remarks</span></span>

<span data-ttu-id="8d119-122">客户端使用**[HrOpenOfflineObj](hropenofflineobj.md)** 打开并获取支持**IMAPIOfflineMgr**脱机对象。</span><span class="sxs-lookup"><span data-stu-id="8d119-122">A client uses **[HrOpenOfflineObj](hropenofflineobj.md)** to open and obtain an offline object that supports **IMAPIOfflineMgr**.</span></span> <span data-ttu-id="8d119-123">由于**IMAPIOfflineMgr**继承从[iunknown 导出](http://msdn.microsoft.com/zh-cn/library/ms680509%28v=VS.85%29.aspx)，客户端可以此接口查询 （通过使用[IUnknown::QueryInterface](http://msdn.microsoft.com/zh-cn/library/ms682521%28v=VS.85%29.aspx)） 来获取**IMAPIOffline**脱机对象指向的接口指针的指针。</span><span class="sxs-lookup"><span data-stu-id="8d119-123">Because **IMAPIOfflineMgr** inherits from [IUnknown](http://msdn.microsoft.com/zh-cn/library/ms680509%28v=VS.85%29.aspx), the client can query this interface (by using [IUnknown::QueryInterface](http://msdn.microsoft.com/zh-cn/library/ms682521%28v=VS.85%29.aspx)) to obtain a pointer to the interface pointer for **IMAPIOffline** for the offline object.</span></span> <span data-ttu-id="8d119-124">客户端然后可以获取或设置对象的当前状态或找出有关对象的回调功能 （通过调用**IMAPIOffline::GetCapabilities** ） 并选择使用**[IMAPIOfflineMgr](imapiofflinemgrimapioffline.md)** 设置回调。</span><span class="sxs-lookup"><span data-stu-id="8d119-124">The client can then get or set the current state of the object, or find out about the callback capabilities of the object (by calling **IMAPIOffline::GetCapabilities** ) and choose to set up callbacks by using **[IMAPIOfflineMgr](imapiofflinemgrimapioffline.md)**.</span></span> 
  
<span data-ttu-id="8d119-125">此接口中的成员保留供内部使用的 Microsoft Outlook 2013 的占位符并可能会更改。</span><span class="sxs-lookup"><span data-stu-id="8d119-125">A member in this interface is a placeholder reserved for the internal use of Microsoft Outlook 2013 and is subject to change.</span></span> <span data-ttu-id="8d119-126">必须只记录使用此接口中的其他成员。</span><span class="sxs-lookup"><span data-stu-id="8d119-126">Other members in this interface must be used only as documented.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="8d119-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8d119-127">See also</span></span>



[<span data-ttu-id="8d119-128">IMAPIOfflineMgr: IMAPIOffline</span><span class="sxs-lookup"><span data-stu-id="8d119-128">IMAPIOfflineMgr : IMAPIOffline</span></span>](imapiofflinemgrimapioffline.md)


[<span data-ttu-id="8d119-129">有关脱机状态 API</span><span class="sxs-lookup"><span data-stu-id="8d119-129">About the Offline State API</span></span>](about-the-offline-state-api.md)
  
[<span data-ttu-id="8d119-130">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="8d119-130">MAPI Constants</span></span>](mapi-constants.md)
  
[<span data-ttu-id="8d119-131">MAPI 接口</span><span class="sxs-lookup"><span data-stu-id="8d119-131">MAPI Interfaces</span></span>](mapi-interfaces.md)

