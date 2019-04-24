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
description: 上次修改时间：2012 年 6 月 25 日
ms.openlocfilehash: 4440df4b8e4a46e13748cf47d599e16599aaf858
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32270082"
---
# <a name="imapiofflinenotifynotify"></a><span data-ttu-id="79892-103">IMAPIOfflineNotify::Notify</span><span class="sxs-lookup"><span data-stu-id="79892-103">IMAPIOfflineNotify::Notify</span></span>

  
  
<span data-ttu-id="79892-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="79892-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="79892-105">向客户端发送有关连接状态更改的通知。</span><span class="sxs-lookup"><span data-stu-id="79892-105">Sends notifications to the client about changes in connection state.</span></span>
  
```cpp
void STDMETHODCALLTYPE Notify(  
    const MAPIOFFLINE_NOTIFY * pNotifyInfo 
);
```

## <a name="parameters"></a><span data-ttu-id="79892-106">参数</span><span class="sxs-lookup"><span data-stu-id="79892-106">Parameters</span></span>

 <span data-ttu-id="79892-107">_pNotifyInfo_</span><span class="sxs-lookup"><span data-stu-id="79892-107">_pNotifyInfo_</span></span>
  
> <span data-ttu-id="79892-108">实时Outlook 发送到客户端的通知。</span><span class="sxs-lookup"><span data-stu-id="79892-108">[in] The notification that Outlook sends to the client.</span></span> <span data-ttu-id="79892-109">通知指示已更改的连接状态部分、旧的连接状态和新的连接状态。</span><span class="sxs-lookup"><span data-stu-id="79892-109">The notification indicates the part of the connection state that has changed, the old connection state, and the new connection state.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="79892-110">注解</span><span class="sxs-lookup"><span data-stu-id="79892-110">Remarks</span></span>

<span data-ttu-id="79892-111">Outlook 使用此方法向客户端发送通知回调。</span><span class="sxs-lookup"><span data-stu-id="79892-111">Outlook uses this method to send notification callbacks to a client.</span></span> <span data-ttu-id="79892-112">若要使此接口可用于 Microsoft outlook 2010 或 microsoft outlook 2013, 客户端必须实现此接口, 并在设置使用 IMAPIOfflineMgr:: 建议的回调时, 将指针作为**[MAPIOFFLINE_ADVISEINFO](mapioffline_adviseinfo.md)** 中的成员传递给该接口**[::!](imapiofflinemgr-advise.md)**.</span><span class="sxs-lookup"><span data-stu-id="79892-112">To make this interface available to Microsoft Outlook 2010 or Microsoft Outlook 2013, the client must implement this interface and pass a pointer to it as a member in **[MAPIOFFLINE_ADVISEINFO](mapioffline_adviseinfo.md)** when setting up callbacks using **[IMAPIOfflineMgr::Advise](imapiofflinemgr-advise.md)**.</span></span> 
  
<span data-ttu-id="79892-113">客户端还会传递给**MAPIOFFLINE_ADVISEINFO**一个客户端令牌, outlook 2010 或 outlook 2013 在 IMAPIOfflineNotify 中使用 **:: Notify**标识为通知回调注册的客户端。</span><span class="sxs-lookup"><span data-stu-id="79892-113">The client also passes to **MAPIOFFLINE_ADVISEINFO** a client token that Outlook 2010 or Outlook 2013 uses in **IMAPIOfflineNotify::Notify** to identify the client registered for the notification callback.</span></span> 
  
<span data-ttu-id="79892-114">通常情况下, outlook 2010 和 outlook 2013 可以通知客户端的联机/脱机更改和其他连接状态更改, 但脱机状态 API 仅支持联机/脱机更改的通知。</span><span class="sxs-lookup"><span data-stu-id="79892-114">In general, Outlook 2010 and Outlook 2013 can notify a client of online/offline changes and other connection state changes, but the Offline State API supports only notifications for online/offline changes.</span></span> <span data-ttu-id="79892-115">客户端必须忽略所有其他通知。</span><span class="sxs-lookup"><span data-stu-id="79892-115">The client must ignore all other notifications.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="79892-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="79892-116">See also</span></span>



[<span data-ttu-id="79892-117">关于脱机状态 API</span><span class="sxs-lookup"><span data-stu-id="79892-117">About the Offline State API</span></span>](about-the-offline-state-api.md)
  
[<span data-ttu-id="79892-118">MAPIOFFLINE_NOTIFY</span><span class="sxs-lookup"><span data-stu-id="79892-118">MAPIOFFLINE_NOTIFY</span></span>](mapioffline_notify.md)

