---
title: IMAPIOfflineNotifyNotify
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIOfflineNotify.Notify
api_type:
- COM
ms.assetid: 10c7cb9d-2e9d-72eb-6b07-31eed892e646
description: 上次修改时间： 2012 年 6 月 25 日
ms.openlocfilehash: 54843339c6843e075ec769da5751ae2fe753f302
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775513"
---
# <a name="imapiofflinenotifynotify"></a><span data-ttu-id="24fb8-103">IMAPIOfflineNotify::Notify</span><span class="sxs-lookup"><span data-stu-id="24fb8-103">IMAPIOfflineNotify::Notify</span></span>

  
  
<span data-ttu-id="24fb8-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="24fb8-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="24fb8-105">将通知发送到客户端有关连接状态的变化。</span><span class="sxs-lookup"><span data-stu-id="24fb8-105">Sends notifications to the client about changes in connection state.</span></span>
  
```cpp
void STDMETHODCALLTYPE Notify(  
    const MAPIOFFLINE_NOTIFY * pNotifyInfo 
);
```

## <a name="parameters"></a><span data-ttu-id="24fb8-106">参数</span><span class="sxs-lookup"><span data-stu-id="24fb8-106">Parameters</span></span>

 <span data-ttu-id="24fb8-107">_pNotifyInfo_</span><span class="sxs-lookup"><span data-stu-id="24fb8-107">_pNotifyInfo_</span></span>
  
> <span data-ttu-id="24fb8-108">[in]在 Outlook 发送到客户端的通知。</span><span class="sxs-lookup"><span data-stu-id="24fb8-108">[in] The notification that Outlook sends to the client.</span></span> <span data-ttu-id="24fb8-109">通知指示已更改的连接状态、 旧的连接状态和新的连接状态的一部分。</span><span class="sxs-lookup"><span data-stu-id="24fb8-109">The notification indicates the part of the connection state that has changed, the old connection state, and the new connection state.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="24fb8-110">说明</span><span class="sxs-lookup"><span data-stu-id="24fb8-110">Remarks</span></span>

<span data-ttu-id="24fb8-111">Outlook 使用此方法向客户发送通知回调。</span><span class="sxs-lookup"><span data-stu-id="24fb8-111">Outlook uses this method to send notification callbacks to a client.</span></span> <span data-ttu-id="24fb8-112">若要使此接口可供 Microsoft Outlook 2010 或 Microsoft Outlook 2013，客户端必须实现此接口并将指针传递给它为**[MAPIOFFLINE_ADVISEINFO](mapioffline_adviseinfo.md)** 中的成员设置使用**[IMAPIOfflineMgr::Advise 回调时](imapiofflinemgr-advise.md)**.</span><span class="sxs-lookup"><span data-stu-id="24fb8-112">To make this interface available to Microsoft Outlook 2010 or Microsoft Outlook 2013, the client must implement this interface and pass a pointer to it as a member in **[MAPIOFFLINE_ADVISEINFO](mapioffline_adviseinfo.md)** when setting up callbacks using **[IMAPIOfflineMgr::Advise](imapiofflinemgr-advise.md)**.</span></span> 
  
<span data-ttu-id="24fb8-113">客户端也将传递给**MAPIOFFLINE_ADVISEINFO**客户端令牌的 Outlook 2010 或 Outlook 2013 使用**IMAPIOfflineNotify::Notify**中标识为通知回调注册的客户端。</span><span class="sxs-lookup"><span data-stu-id="24fb8-113">The client also passes to **MAPIOFFLINE_ADVISEINFO** a client token that Outlook 2010 or Outlook 2013 uses in **IMAPIOfflineNotify::Notify** to identify the client registered for the notification callback.</span></span> 
  
<span data-ttu-id="24fb8-114">一般情况下，Outlook 2010 和 Outlook 2013 可以通知的联机/脱机更改客户端和其他连接的状态更改，但脱机状态 API 支持仅通知联机/脱机的更改。</span><span class="sxs-lookup"><span data-stu-id="24fb8-114">In general, Outlook 2010 and Outlook 2013 can notify a client of online/offline changes and other connection state changes, but the Offline State API supports only notifications for online/offline changes.</span></span> <span data-ttu-id="24fb8-115">客户端必须忽略所有其他通知。</span><span class="sxs-lookup"><span data-stu-id="24fb8-115">The client must ignore all other notifications.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="24fb8-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="24fb8-116">See also</span></span>



[<span data-ttu-id="24fb8-117">关于脱机状态 API</span><span class="sxs-lookup"><span data-stu-id="24fb8-117">About the Offline State API</span></span>](about-the-offline-state-api.md)
  
[<span data-ttu-id="24fb8-118">MAPIOFFLINE_NOTIFY</span><span class="sxs-lookup"><span data-stu-id="24fb8-118">MAPIOFFLINE_NOTIFY</span></span>](mapioffline_notify.md)

