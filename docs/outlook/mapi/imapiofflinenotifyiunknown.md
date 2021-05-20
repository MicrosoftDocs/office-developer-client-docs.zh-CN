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
ms.openlocfilehash: 940cf0cf377f1b38071df5e3c300ccb7d685e5a2
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33439875"
---
# <a name="imapiofflinenotify--iunknown"></a><span data-ttu-id="4ff33-103">IMAPIOfflineNotify : IUnknown</span><span class="sxs-lookup"><span data-stu-id="4ff33-103">IMAPIOfflineNotify : IUnknown</span></span>

  
  
<span data-ttu-id="4ff33-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="4ff33-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="4ff33-105">支持Microsoft Outlook 2010 Microsoft Outlook 2013客户端发送通知回调。</span><span class="sxs-lookup"><span data-stu-id="4ff33-105">Supports Microsoft Outlook 2010 and Microsoft Outlook 2013 in sending notification callbacks to a client.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="4ff33-106">提供者：</span><span class="sxs-lookup"><span data-stu-id="4ff33-106">Provided by:</span></span>  <br/> |<span data-ttu-id="4ff33-107">客户端</span><span class="sxs-lookup"><span data-stu-id="4ff33-107">Client</span></span>  <br/> |
|<span data-ttu-id="4ff33-108">接口标识符：</span><span class="sxs-lookup"><span data-stu-id="4ff33-108">Interface identifier:</span></span>  <br/> |<span data-ttu-id="4ff33-109">IID_IMAPIOfflineNotify</span><span class="sxs-lookup"><span data-stu-id="4ff33-109">IID_IMAPIOfflineNotify</span></span>  <br/> |
   
## <a name="vtable-order"></a><span data-ttu-id="4ff33-110">Vtable 顺序</span><span class="sxs-lookup"><span data-stu-id="4ff33-110">Vtable order</span></span>

|||
|:-----|:-----|
|[<span data-ttu-id="4ff33-111">Notify</span><span class="sxs-lookup"><span data-stu-id="4ff33-111">Notify</span></span>](imapiofflinenotify-notify.md) <br/> |<span data-ttu-id="4ff33-112">向客户端发送有关连接状态更改的通知。</span><span class="sxs-lookup"><span data-stu-id="4ff33-112">Sends notifications to a client about changes in connection state.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="4ff33-113">备注</span><span class="sxs-lookup"><span data-stu-id="4ff33-113">Remarks</span></span>

<span data-ttu-id="4ff33-114">当使用 **[IMAPIOfflineMgr：：Advise](imapiofflinemgr-advise.md)** 设置回调时 **[](mapioffline_adviseinfo.md)**，客户端必须实现此接口，并作为 MAPIOFFLINE_ADVISEINFO 中的成员传递指向它的指针。</span><span class="sxs-lookup"><span data-stu-id="4ff33-114">The client must implement this interface and pass a pointer to it as a member in **[MAPIOFFLINE_ADVISEINFO](mapioffline_adviseinfo.md)** when setting up callbacks using **[IMAPIOfflineMgr::Advise](imapiofflinemgr-advise.md)**.</span></span> <span data-ttu-id="4ff33-115">随后，Outlook 2010 Outlook 2013 将能够使用此接口向客户端发送通知回调。</span><span class="sxs-lookup"><span data-stu-id="4ff33-115">Subsequently, Outlook 2010 or Outlook 2013 will be able to use this interface to send notification callbacks to the client.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="4ff33-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4ff33-116">See also</span></span>



[<span data-ttu-id="4ff33-117">IMAPIOfflineMgr::Advise</span><span class="sxs-lookup"><span data-stu-id="4ff33-117">IMAPIOfflineMgr::Advise</span></span>](imapiofflinemgr-advise.md)


[<span data-ttu-id="4ff33-118">关于脱机状态 API</span><span class="sxs-lookup"><span data-stu-id="4ff33-118">About the Offline State API</span></span>](about-the-offline-state-api.md)
  
[<span data-ttu-id="4ff33-119">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="4ff33-119">MAPI Constants</span></span>](mapi-constants.md)
  
[<span data-ttu-id="4ff33-120">MAPIOFFLINE_ADVISEINFO</span><span class="sxs-lookup"><span data-stu-id="4ff33-120">MAPIOFFLINE_ADVISEINFO</span></span>](mapioffline_adviseinfo.md)

