---
title: 关于脱机状态 API
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: 18b0d284-c224-a022-47d9-b2d82a32f996
description: 上次修改时间： 2012 年 6 月 25 日
ms.openlocfilehash: df225a0852b09e048656e817c54ea28b0de59888
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774492"
---
# <a name="about-the-offline-state-api"></a><span data-ttu-id="3e0d2-103">关于脱机状态 API</span><span class="sxs-lookup"><span data-stu-id="3e0d2-103">About the Offline State API</span></span>

  
  
<span data-ttu-id="3e0d2-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="3e0d2-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="3e0d2-105">脱机状态 API 支持指示 Microsoft Outlook 2013 和 Microsoft Outlook 2010 中的用户的连接状态的变化的回调 — 例如，从要在 Outlook 2013 或 Outlook 2010 中的联机到脱机。</span><span class="sxs-lookup"><span data-stu-id="3e0d2-105">The Offline State API supports callbacks indicating changes in a user's connection state in Microsoft Outlook 2013 and Microsoft Outlook 2010—for example, from being online in Outlook 2013 or Outlook 2010 to being offline.</span></span> <span data-ttu-id="3e0d2-106">API 使用 Outlook 2013 或 Outlook 2010 中的全局脱机对象来跟踪此更改为给定的用户帐户配置文件。</span><span class="sxs-lookup"><span data-stu-id="3e0d2-106">The API uses a global offline object in Outlook 2013 or Outlook 2010 to track such changes for a given user account profile.</span></span> <span data-ttu-id="3e0d2-107">通知是回调的唯一受支持的设备。</span><span class="sxs-lookup"><span data-stu-id="3e0d2-107">Notification is the only supported form of callback.</span></span> <span data-ttu-id="3e0d2-108">此 api 的客户端，为邮件提供商希望此类连接状态更改通知执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="3e0d2-108">As clients of this API, mail providers who want to be notified of such connection state changes do the following:</span></span>
  
1. <span data-ttu-id="3e0d2-109">实现**[IMAPIOfflineNotify](imapiofflinenotifyiunknown.md)**。</span><span class="sxs-lookup"><span data-stu-id="3e0d2-109">Implement **[IMAPIOfflineNotify](imapiofflinenotifyiunknown.md)**.</span></span> 
    
2. <span data-ttu-id="3e0d2-110">打开现有脱机使用**[HrOpenOfflineObj](hropenofflineobj.md)** 特定配置文件对象。</span><span class="sxs-lookup"><span data-stu-id="3e0d2-110">Open an existing offline object for a specific profile using **[HrOpenOfflineObj](hropenofflineobj.md)**.</span></span> 
    
3. <span data-ttu-id="3e0d2-111">确定对象是否有能力提供联机或脱机使用**[IMAPIOffline::GetCapabilities](imapioffline-getcapabilities.md)** 的通知。</span><span class="sxs-lookup"><span data-stu-id="3e0d2-111">Determine if the object has the capability of providing online or offline notifications using **[IMAPIOffline::GetCapabilities](imapioffline-getcapabilities.md)**.</span></span> 
    
4. <span data-ttu-id="3e0d2-112">注册使用**[IMAPIOfflineMgr::Advise](imapiofflinemgr-advise.md)** 联机或脱机通知的对象。</span><span class="sxs-lookup"><span data-stu-id="3e0d2-112">Register the object for online or offline notifications using **[IMAPIOfflineMgr::Advise](imapiofflinemgr-advise.md)**.</span></span> <span data-ttu-id="3e0d2-113">邮件提供商现在可以接收通知 Outlook 2013 或 Outlook 2010 发送使用**IMAPIOfflineNotify**。</span><span class="sxs-lookup"><span data-stu-id="3e0d2-113">Mail providers can now receive notifications that Outlook 2013 or Outlook 2010 send using **IMAPIOfflineNotify**.</span></span> 
    
5. <span data-ttu-id="3e0d2-114">在关闭，删除注册联机和脱机使用**[IMAPIOfflineMgr::Unadvise](imapiofflinemgr-unadvise.md)** 的通知。</span><span class="sxs-lookup"><span data-stu-id="3e0d2-114">On shutdown, remove registration for online and offline notifications using **[IMAPIOfflineMgr::Unadvise](imapiofflinemgr-unadvise.md)**.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="3e0d2-115">一般情况下，Outlook 2013 和 Outlook 2010，则可以向联机/脱机的更改以及其他更改，客户端的通知，但脱机状态 API 支持仅通知联机/脱机的更改。</span><span class="sxs-lookup"><span data-stu-id="3e0d2-115">In general, Outlook 2013 and Outlook 2010 can notify a client of online/offline changes as well as other changes, but the Offline State API supports only notifications for online/offline changes.</span></span> <span data-ttu-id="3e0d2-116">客户端应忽略所有其他通知。</span><span class="sxs-lookup"><span data-stu-id="3e0d2-116">The client should ignore all other notifications.</span></span> <span data-ttu-id="3e0d2-117">有关详细信息，请参阅**[IMAPIOfflineNotify::Notify](imapiofflinenotify-notify.md)** 和**[MAPIOFFLINE_NOTIFY](mapioffline_notify.md)**。</span><span class="sxs-lookup"><span data-stu-id="3e0d2-117">For more information, see **[IMAPIOfflineNotify::Notify](imapiofflinenotify-notify.md)** and **[MAPIOFFLINE_NOTIFY](mapioffline_notify.md)**.</span></span> 
  
 <span data-ttu-id="3e0d2-118">有关使用脱机状态 API 的客户端的示例，请参阅[有关示例脱机状态外接程序](about-the-sample-offline-state-add-in.md)。</span><span class="sxs-lookup"><span data-stu-id="3e0d2-118">For an example of a client that uses the Offline State API, see [About the Sample Offline State Add-in](about-the-sample-offline-state-add-in.md).</span></span> <span data-ttu-id="3e0d2-119">示例脱机状态加载项是使用脱机状态 API 来监控并更改连接状态的 COM 加载项。</span><span class="sxs-lookup"><span data-stu-id="3e0d2-119">The Sample Offline State Add-in is a COM add-in that uses the Offline State API to monitor and change the connection state.</span></span>
  
<span data-ttu-id="3e0d2-120">此 API 提供下列功能：</span><span class="sxs-lookup"><span data-stu-id="3e0d2-120">This API provides the following:</span></span>
  
<span data-ttu-id="3e0d2-121">定义：</span><span class="sxs-lookup"><span data-stu-id="3e0d2-121">Definitions:</span></span>
  
- [<span data-ttu-id="3e0d2-122">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="3e0d2-122">MAPI Constants</span></span>](mapi-constants.md)
    
<span data-ttu-id="3e0d2-123">数据类型：</span><span class="sxs-lookup"><span data-stu-id="3e0d2-123">Data types:</span></span>
  
- <span data-ttu-id="3e0d2-124">**[MAPIOFFLINE_ADVISEINFO](mapioffline_adviseinfo.md)**</span><span class="sxs-lookup"><span data-stu-id="3e0d2-124">**[MAPIOFFLINE_ADVISEINFO](mapioffline_adviseinfo.md)**</span></span>
    
- <span data-ttu-id="3e0d2-125">**[MAPIOFFLINE_CALLBACK_TYPE](mapioffline_callback_type.md)**</span><span class="sxs-lookup"><span data-stu-id="3e0d2-125">**[MAPIOFFLINE_CALLBACK_TYPE](mapioffline_callback_type.md)**</span></span>
    
- <span data-ttu-id="3e0d2-126">**[MAPIOFFLINE_NOTIFY](mapioffline_notify.md)**</span><span class="sxs-lookup"><span data-stu-id="3e0d2-126">**[MAPIOFFLINE_NOTIFY](mapioffline_notify.md)**</span></span>
    
<span data-ttu-id="3e0d2-127">函数：</span><span class="sxs-lookup"><span data-stu-id="3e0d2-127">Functions:</span></span>
  
- <span data-ttu-id="3e0d2-128">**[HrOpenOfflineObj](hropenofflineobj.md)**</span><span class="sxs-lookup"><span data-stu-id="3e0d2-128">**[HrOpenOfflineObj](hropenofflineobj.md)**</span></span>
    
<span data-ttu-id="3e0d2-129">接口：</span><span class="sxs-lookup"><span data-stu-id="3e0d2-129">Interfaces:</span></span>
  
- <span data-ttu-id="3e0d2-130">**[IMAPIOffline](imapiofflineiunknown.md)**</span><span class="sxs-lookup"><span data-stu-id="3e0d2-130">**[IMAPIOffline](imapiofflineiunknown.md)**</span></span>
    
- <span data-ttu-id="3e0d2-131">**[IMAPIOfflineMgr](imapiofflinemgrimapioffline.md)**</span><span class="sxs-lookup"><span data-stu-id="3e0d2-131">**[IMAPIOfflineMgr](imapiofflinemgrimapioffline.md)**</span></span>
    
- <span data-ttu-id="3e0d2-132">**[IMAPIOfflineNotify](imapiofflinenotifyiunknown.md)**</span><span class="sxs-lookup"><span data-stu-id="3e0d2-132">**[IMAPIOfflineNotify](imapiofflinenotifyiunknown.md)**</span></span>
    

