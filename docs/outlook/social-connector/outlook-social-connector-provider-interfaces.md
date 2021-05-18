---
title: OutlookSocial Connector 提供程序接口
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 8f92b2c7-9f47-4c84-874b-fec1a2a5b555
description: Outlook Social Connector (OSC) 是 Office 客户端应用程序共享的一项 Office 功能，连接到社交和业务网络，以便用户无需离开 Office 即可与网络中人员保持联系。
ms.openlocfilehash: 77759db34f63239473e0682cfaca720860e96768
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33422808"
---
# <a name="outlook-social-connector-provider-interfaces"></a><span data-ttu-id="0ad51-103">OutlookSocial Connector 提供程序接口</span><span class="sxs-lookup"><span data-stu-id="0ad51-103">Outlook Social Connector provider interfaces</span></span>

<span data-ttu-id="0ad51-104">Outlook Social Connector (OSC) 是 Office 客户端应用程序共享的一项 Office 功能，连接到社交和业务网络，以便用户无需离开 Office 即可与网络中人员保持联系。</span><span class="sxs-lookup"><span data-stu-id="0ad51-104">The Outlook Social Connector (OSC) is an Office feature shared by Office client applications that connects to social and business networks so users can stay in touch with the people in their networks without leaving Office.</span></span> 
  
<span data-ttu-id="0ad51-105">OSC 提供程序是组件对象模型 (COM) DLL，它允许 OSC 以独立于每个社交网络的 API 的方式访问社交网络数据。</span><span class="sxs-lookup"><span data-stu-id="0ad51-105">An OSC provider is a Component Object Model (COM) DLL that allows the OSC to access social network data in a way that is independent of the APIs of each social network.</span></span> <span data-ttu-id="0ad51-106">下表列出了 OSC 提供程序可扩展性中的接口。</span><span class="sxs-lookup"><span data-stu-id="0ad51-106">The following table lists the interfaces in OSC provider extensibility.</span></span> <span data-ttu-id="0ad51-107">OSC 提供程序必须实现与 OSC 通信的五个接口中的四个：ISocialPerson、ISocialProfile、ISocialProvider 和[ISocialSession。](isocialsessioniunknown.md) [](isocialpersoniunknown.md) [](isocialprofileisocialperson.md) [](isocialprovideriunknown.md)</span><span class="sxs-lookup"><span data-stu-id="0ad51-107">An OSC provider must implement four of the five interfaces to communicate with the OSC: [ISocialPerson](isocialpersoniunknown.md), [ISocialProfile](isocialprofileisocialperson.md), [ISocialProvider](isocialprovideriunknown.md), and [ISocialSession](isocialsessioniunknown.md).</span></span> <span data-ttu-id="0ad51-108">如果 OSC 提供程序支持同步活动、好友按需或混合同步、缓存登录凭据和使用缓存凭据登录，或者支持关注某人，则提供程序也应该实现[ISocialSession2。](isocialsession2iunknown.md)</span><span class="sxs-lookup"><span data-stu-id="0ad51-108">If the OSC provider supports synchronizing activities, on-demand or hybrid synchronization of friends, caching logon credentials and logging on using cached credentials, or the ability to follow a person, the provider should implement [ISocialSession2](isocialsession2iunknown.md), as well.</span></span>
  
|<span data-ttu-id="0ad51-109">**名称**</span><span class="sxs-lookup"><span data-stu-id="0ad51-109">**Name**</span></span>|<span data-ttu-id="0ad51-110">**说明**</span><span class="sxs-lookup"><span data-stu-id="0ad51-110">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="0ad51-111">ISocialPerson</span><span class="sxs-lookup"><span data-stu-id="0ad51-111">ISocialPerson</span></span>](isocialpersoniunknown.md) <br/> |<span data-ttu-id="0ad51-112">表示社交网络上的人员。</span><span class="sxs-lookup"><span data-stu-id="0ad51-112">Represents a person on the social network.</span></span>  <br/> |
|[<span data-ttu-id="0ad51-113">ISocialProfile</span><span class="sxs-lookup"><span data-stu-id="0ad51-113">ISocialProfile</span></span>](isocialprofileisocialperson.md) <br/> |<span data-ttu-id="0ad51-114">表示已登录的用户。</span><span class="sxs-lookup"><span data-stu-id="0ad51-114">Represents the logged-on user.</span></span>  <br/> |
|[<span data-ttu-id="0ad51-115">ISocialProvider</span><span class="sxs-lookup"><span data-stu-id="0ad51-115">ISocialProvider</span></span>](isocialprovideriunknown.md) <br/> |<span data-ttu-id="0ad51-116">表示 OSC 提供程序的实例。</span><span class="sxs-lookup"><span data-stu-id="0ad51-116">Represents an instance of an OSC provider.</span></span>  <br/> |
|[<span data-ttu-id="0ad51-117">ISocialSession</span><span class="sxs-lookup"><span data-stu-id="0ad51-117">ISocialSession</span></span>](isocialsessioniunknown.md) <br/> |<span data-ttu-id="0ad51-118">表示与社交网络网站的连接。</span><span class="sxs-lookup"><span data-stu-id="0ad51-118">Represents a connection to a social network site.</span></span>  <br/> |
|[<span data-ttu-id="0ad51-119">ISocialSession2</span><span class="sxs-lookup"><span data-stu-id="0ad51-119">ISocialSession2</span></span>](isocialsession2iunknown.md) <br/> |<span data-ttu-id="0ad51-120">支持同步活动、添加好友、按需或混合同步好友，或者使用缓存凭据登录社交网络。</span><span class="sxs-lookup"><span data-stu-id="0ad51-120">Supports synchronizing activities, adding friends, on-demand or hybrid synchronization of friends, or logging on to the social network by using cached credentials.</span></span>  <br/> |
   

