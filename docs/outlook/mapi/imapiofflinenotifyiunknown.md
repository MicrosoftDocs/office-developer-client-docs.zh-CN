---
title: IMAPIOfflineNotify IUnknown
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIOfflineNotify
api_type:
- COM
ms.assetid: a593d2a1-29f8-7e23-85bf-02fa3cfebe1b
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: adcb8e78d4e85e19d4102795aa4d43f06a7f86ba
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22568145"
---
# <a name="imapiofflinenotify--iunknown"></a><span data-ttu-id="3cc75-103">IMAPIOfflineNotify : IUnknown</span><span class="sxs-lookup"><span data-stu-id="3cc75-103">IMAPIOfflineNotify : IUnknown</span></span>

  
  
<span data-ttu-id="3cc75-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="3cc75-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="3cc75-105">支持 Microsoft Outlook 2010 和 Microsoft Outlook 2013 中向客户端发送通知回调。</span><span class="sxs-lookup"><span data-stu-id="3cc75-105">Supports Microsoft Outlook 2010 and Microsoft Outlook 2013 in sending notification callbacks to a client.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="3cc75-106">提供者：</span><span class="sxs-lookup"><span data-stu-id="3cc75-106">Provided by:</span></span>  <br/> |<span data-ttu-id="3cc75-107">客户端</span><span class="sxs-lookup"><span data-stu-id="3cc75-107">Client</span></span>  <br/> |
|<span data-ttu-id="3cc75-108">接口标识符：</span><span class="sxs-lookup"><span data-stu-id="3cc75-108">Interface identifier:</span></span>  <br/> |<span data-ttu-id="3cc75-109">IID_IMAPIOfflineNotify</span><span class="sxs-lookup"><span data-stu-id="3cc75-109">IID_IMAPIOfflineNotify</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="3cc75-110">Vtable 顺序排列</span><span class="sxs-lookup"><span data-stu-id="3cc75-110">Vtable order</span></span>

|||
|:-----|:-----|
|[<span data-ttu-id="3cc75-111">Notify</span><span class="sxs-lookup"><span data-stu-id="3cc75-111">Notify</span></span>](imapiofflinenotify-notify.md) <br/> |<span data-ttu-id="3cc75-112">将通知发送到客户端有关连接状态的变化。</span><span class="sxs-lookup"><span data-stu-id="3cc75-112">Sends notifications to a client about changes in connection state.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="3cc75-113">注解</span><span class="sxs-lookup"><span data-stu-id="3cc75-113">Remarks</span></span>

<span data-ttu-id="3cc75-114">客户端必须实现此接口，并将指针传递给它为**[MAPIOFFLINE_ADVISEINFO](mapioffline_adviseinfo.md)** 中的成员设置使用**[IMAPIOfflineMgr::Advise](imapiofflinemgr-advise.md)** 回调时。</span><span class="sxs-lookup"><span data-stu-id="3cc75-114">The client must implement this interface and pass a pointer to it as a member in **[MAPIOFFLINE_ADVISEINFO](mapioffline_adviseinfo.md)** when setting up callbacks using **[IMAPIOfflineMgr::Advise](imapiofflinemgr-advise.md)**.</span></span> <span data-ttu-id="3cc75-115">随后，Outlook 2010 或 Outlook 2013 都将能够使用此接口到客户端发送通知回调。</span><span class="sxs-lookup"><span data-stu-id="3cc75-115">Subsequently, Outlook 2010 or Outlook 2013 will be able to use this interface to send notification callbacks to the client.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="3cc75-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3cc75-116">See also</span></span>



[<span data-ttu-id="3cc75-117">IMAPIOfflineMgr::Advise</span><span class="sxs-lookup"><span data-stu-id="3cc75-117">IMAPIOfflineMgr::Advise</span></span>](imapiofflinemgr-advise.md)


[<span data-ttu-id="3cc75-118">关于脱机状态 API</span><span class="sxs-lookup"><span data-stu-id="3cc75-118">About the Offline State API</span></span>](about-the-offline-state-api.md)
  
[<span data-ttu-id="3cc75-119">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="3cc75-119">MAPI Constants</span></span>](mapi-constants.md)
  
[<span data-ttu-id="3cc75-120">MAPIOFFLINE_ADVISEINFO</span><span class="sxs-lookup"><span data-stu-id="3cc75-120">MAPIOFFLINE_ADVISEINFO</span></span>](mapioffline_adviseinfo.md)

