---
title: 关于脱机状态 API
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: 18b0d284-c224-a022-47d9-b2d82a32f996
description: 上次修改时间：2012 年 6 月 25 日
ms.openlocfilehash: 56793ae0d2c2ce76c89c7cda4985618e3a40ccfd
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33410481"
---
# <a name="about-the-offline-state-api"></a><span data-ttu-id="21321-103">关于脱机状态 API</span><span class="sxs-lookup"><span data-stu-id="21321-103">About the Offline State API</span></span>

  
  
<span data-ttu-id="21321-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="21321-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="21321-105">脱机状态 API 支持回调指示用户的连接状态在 microsoft outlook 2013 和 microsoft outlook 2010 中的更改, 例如, 在 outlook 2013 中联机或 outlook 2010 脱机。</span><span class="sxs-lookup"><span data-stu-id="21321-105">The Offline State API supports callbacks indicating changes in a user's connection state in Microsoft Outlook 2013 and Microsoft Outlook 2010—for example, from being online in Outlook 2013 or Outlook 2010 to being offline.</span></span> <span data-ttu-id="21321-106">API 在 outlook 2013 或 outlook 2010 中使用全局脱机对象跟踪给定用户帐户配置文件的此类更改。</span><span class="sxs-lookup"><span data-stu-id="21321-106">The API uses a global offline object in Outlook 2013 or Outlook 2010 to track such changes for a given user account profile.</span></span> <span data-ttu-id="21321-107">通知是唯一受支持的回调形式。</span><span class="sxs-lookup"><span data-stu-id="21321-107">Notification is the only supported form of callback.</span></span> <span data-ttu-id="21321-108">作为此 API 的客户端, 希望通知这些连接状态更改的邮件提供程序将执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="21321-108">As clients of this API, mail providers who want to be notified of such connection state changes do the following:</span></span>
  
1. <span data-ttu-id="21321-109">实现**[IMAPIOfflineNotify](imapiofflinenotifyiunknown.md)**。</span><span class="sxs-lookup"><span data-stu-id="21321-109">Implement **[IMAPIOfflineNotify](imapiofflinenotifyiunknown.md)**.</span></span> 
    
2. <span data-ttu-id="21321-110">使用**[HrOpenOfflineObj](hropenofflineobj.md)** 打开特定配置文件的现有脱机对象。</span><span class="sxs-lookup"><span data-stu-id="21321-110">Open an existing offline object for a specific profile using **[HrOpenOfflineObj](hropenofflineobj.md)**.</span></span> 
    
3. <span data-ttu-id="21321-111">确定对象是否具有使用**[IMAPIOffline:: GetCapabilities](imapioffline-getcapabilities.md)** 提供联机或脱机通知的功能。</span><span class="sxs-lookup"><span data-stu-id="21321-111">Determine if the object has the capability of providing online or offline notifications using **[IMAPIOffline::GetCapabilities](imapioffline-getcapabilities.md)**.</span></span> 
    
4. <span data-ttu-id="21321-112">使用**[IMAPIOfflineMgr:: 建议](imapiofflinemgr-advise.md)** 为联机通知或脱机通知注册对象。</span><span class="sxs-lookup"><span data-stu-id="21321-112">Register the object for online or offline notifications using **[IMAPIOfflineMgr::Advise](imapiofflinemgr-advise.md)**.</span></span> <span data-ttu-id="21321-113">邮件提供商现在可以使用**IMAPIOfflineNotify**接收 outlook 2013 或 outlook 2010 发送的通知。</span><span class="sxs-lookup"><span data-stu-id="21321-113">Mail providers can now receive notifications that Outlook 2013 or Outlook 2010 send using **IMAPIOfflineNotify**.</span></span> 
    
5. <span data-ttu-id="21321-114">关闭后, 请使用**[IMAPIOfflineMgr:: Unadvise](imapiofflinemgr-unadvise.md)** 删除联机和脱机通知的注册。</span><span class="sxs-lookup"><span data-stu-id="21321-114">On shutdown, remove registration for online and offline notifications using **[IMAPIOfflineMgr::Unadvise](imapiofflinemgr-unadvise.md)**.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="21321-115">通常情况下, outlook 2013 和 outlook 2010 可以通知客户端的联机/脱机更改和其他更改, 但脱机状态 API 仅支持联机/脱机更改的通知。</span><span class="sxs-lookup"><span data-stu-id="21321-115">In general, Outlook 2013 and Outlook 2010 can notify a client of online/offline changes as well as other changes, but the Offline State API supports only notifications for online/offline changes.</span></span> <span data-ttu-id="21321-116">客户端应忽略所有其他通知。</span><span class="sxs-lookup"><span data-stu-id="21321-116">The client should ignore all other notifications.</span></span> <span data-ttu-id="21321-117">有关详细信息, 请参阅**[IMAPIOfflineNotify:: Notify](imapiofflinenotify-notify.md)** and **[MAPIOFFLINE_NOTIFY](mapioffline_notify.md)**。</span><span class="sxs-lookup"><span data-stu-id="21321-117">For more information, see **[IMAPIOfflineNotify::Notify](imapiofflinenotify-notify.md)** and **[MAPIOFFLINE_NOTIFY](mapioffline_notify.md)**.</span></span> 
  
 <span data-ttu-id="21321-118">有关使用脱机状态 API 的客户端的示例, 请参阅[关于示例脱机状态加载项](about-the-sample-offline-state-add-in.md)。</span><span class="sxs-lookup"><span data-stu-id="21321-118">For an example of a client that uses the Offline State API, see [About the Sample Offline State Add-in](about-the-sample-offline-state-add-in.md).</span></span> <span data-ttu-id="21321-119">示例脱机状态外接程序是一个 COM 加载项, 它使用脱机状态 API 监视和更改连接状态。</span><span class="sxs-lookup"><span data-stu-id="21321-119">The Sample Offline State Add-in is a COM add-in that uses the Offline State API to monitor and change the connection state.</span></span>
  
<span data-ttu-id="21321-120">此 API 提供以下内容:</span><span class="sxs-lookup"><span data-stu-id="21321-120">This API provides the following:</span></span>
  
<span data-ttu-id="21321-121">定义：</span><span class="sxs-lookup"><span data-stu-id="21321-121">Definitions:</span></span>
  
- [<span data-ttu-id="21321-122">MAPI 常量</span><span class="sxs-lookup"><span data-stu-id="21321-122">MAPI Constants</span></span>](mapi-constants.md)
    
<span data-ttu-id="21321-123">数据类型:</span><span class="sxs-lookup"><span data-stu-id="21321-123">Data types:</span></span>
  
- <span data-ttu-id="21321-124">**[MAPIOFFLINE_ADVISEINFO](mapioffline_adviseinfo.md)**</span><span class="sxs-lookup"><span data-stu-id="21321-124">**[MAPIOFFLINE_ADVISEINFO](mapioffline_adviseinfo.md)**</span></span>
    
- <span data-ttu-id="21321-125">**[MAPIOFFLINE_CALLBACK_TYPE](mapioffline_callback_type.md)**</span><span class="sxs-lookup"><span data-stu-id="21321-125">**[MAPIOFFLINE_CALLBACK_TYPE](mapioffline_callback_type.md)**</span></span>
    
- <span data-ttu-id="21321-126">**[MAPIOFFLINE_NOTIFY](mapioffline_notify.md)**</span><span class="sxs-lookup"><span data-stu-id="21321-126">**[MAPIOFFLINE_NOTIFY](mapioffline_notify.md)**</span></span>
    
<span data-ttu-id="21321-127">函数：</span><span class="sxs-lookup"><span data-stu-id="21321-127">Functions:</span></span>
  
- <span data-ttu-id="21321-128">**[HrOpenOfflineObj](hropenofflineobj.md)**</span><span class="sxs-lookup"><span data-stu-id="21321-128">**[HrOpenOfflineObj](hropenofflineobj.md)**</span></span>
    
<span data-ttu-id="21321-129">接口：</span><span class="sxs-lookup"><span data-stu-id="21321-129">Interfaces:</span></span>
  
- <span data-ttu-id="21321-130">**[IMAPIOffline](imapiofflineiunknown.md)**</span><span class="sxs-lookup"><span data-stu-id="21321-130">**[IMAPIOffline](imapiofflineiunknown.md)**</span></span>
    
- <span data-ttu-id="21321-131">**[IMAPIOfflineMgr](imapiofflinemgrimapioffline.md)**</span><span class="sxs-lookup"><span data-stu-id="21321-131">**[IMAPIOfflineMgr](imapiofflinemgrimapioffline.md)**</span></span>
    
- <span data-ttu-id="21321-132">**[IMAPIOfflineNotify](imapiofflinenotifyiunknown.md)**</span><span class="sxs-lookup"><span data-stu-id="21321-132">**[IMAPIOfflineNotify](imapiofflinenotifyiunknown.md)**</span></span>
    

