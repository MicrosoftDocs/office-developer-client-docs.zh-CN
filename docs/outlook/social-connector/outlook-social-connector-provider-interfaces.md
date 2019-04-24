---
title: Outlook Social Connector 提供程序接口
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 8f92b2c7-9f47-4c84-874b-fec1a2a5b555
description: Outlook Social Connector (.osc) 是 office 客户端应用程序共享的 office 功能, 用于连接到社交和业务网络, 以便用户可以在不离开 Office 的情况下与他们的网络中的人员保持联系。
ms.openlocfilehash: 77759db34f63239473e0682cfaca720860e96768
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32359848"
---
# <a name="outlook-social-connector-provider-interfaces"></a><span data-ttu-id="fc262-103">Outlook Social Connector 提供程序接口</span><span class="sxs-lookup"><span data-stu-id="fc262-103">Outlook Social Connector provider interfaces</span></span>

<span data-ttu-id="fc262-104">Outlook Social Connector (.osc) 是 office 客户端应用程序共享的 office 功能, 用于连接到社交和业务网络, 以便用户可以在不离开 Office 的情况下与他们的网络中的人员保持联系。</span><span class="sxs-lookup"><span data-stu-id="fc262-104">The Outlook Social Connector (OSC) is an Office feature shared by Office client applications that connects to social and business networks so users can stay in touch with the people in their networks without leaving Office.</span></span> 
  
<span data-ttu-id="fc262-105">.osc 提供程序是一种组件对象模型 (COM) DLL, 它允许 .osc 以独立于每个社交网络的 api 的方式访问社交网络数据。</span><span class="sxs-lookup"><span data-stu-id="fc262-105">An OSC provider is a Component Object Model (COM) DLL that allows the OSC to access social network data in a way that is independent of the APIs of each social network.</span></span> <span data-ttu-id="fc262-106">下表列出了 .osc 提供程序可扩展性中的接口。</span><span class="sxs-lookup"><span data-stu-id="fc262-106">The following table lists the interfaces in OSC provider extensibility.</span></span> <span data-ttu-id="fc262-107">一个 .osc 提供程序必须实现五个接口中的四个, 才能与 .osc: [ISocialPerson](isocialpersoniunknown.md)、 [ISocialProfile](isocialprofileisocialperson.md)、 [ISocialProvider](isocialprovideriunknown.md)和[ISocialSession](isocialsessioniunknown.md)进行通信。</span><span class="sxs-lookup"><span data-stu-id="fc262-107">An OSC provider must implement four of the five interfaces to communicate with the OSC: [ISocialPerson](isocialpersoniunknown.md), [ISocialProfile](isocialprofileisocialperson.md), [ISocialProvider](isocialprovideriunknown.md), and [ISocialSession](isocialsessioniunknown.md).</span></span> <span data-ttu-id="fc262-108">如果 .osc 提供程序支持同步活动、对好友或混合同步访问好友、缓存登录凭据和使用缓存凭据登录, 或者能够关注某个人, 则提供程序应实现[ISocialSession2](isocialsession2iunknown.md), 也是如此。</span><span class="sxs-lookup"><span data-stu-id="fc262-108">If the OSC provider supports synchronizing activities, on-demand or hybrid synchronization of friends, caching logon credentials and logging on using cached credentials, or the ability to follow a person, the provider should implement [ISocialSession2](isocialsession2iunknown.md), as well.</span></span>
  
|<span data-ttu-id="fc262-109">**名称**</span><span class="sxs-lookup"><span data-stu-id="fc262-109">**Name**</span></span>|<span data-ttu-id="fc262-110">**说明**</span><span class="sxs-lookup"><span data-stu-id="fc262-110">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="fc262-111">ISocialPerson</span><span class="sxs-lookup"><span data-stu-id="fc262-111">ISocialPerson</span></span>](isocialpersoniunknown.md) <br/> |<span data-ttu-id="fc262-112">表示社交网络上的人员。</span><span class="sxs-lookup"><span data-stu-id="fc262-112">Represents a person on the social network.</span></span>  <br/> |
|[<span data-ttu-id="fc262-113">ISocialProfile</span><span class="sxs-lookup"><span data-stu-id="fc262-113">ISocialProfile</span></span>](isocialprofileisocialperson.md) <br/> |<span data-ttu-id="fc262-114">表示已登录的用户。</span><span class="sxs-lookup"><span data-stu-id="fc262-114">Represents the logged-on user.</span></span>  <br/> |
|[<span data-ttu-id="fc262-115">ISocialProvider</span><span class="sxs-lookup"><span data-stu-id="fc262-115">ISocialProvider</span></span>](isocialprovideriunknown.md) <br/> |<span data-ttu-id="fc262-116">表示一个 .osc 提供程序的实例。</span><span class="sxs-lookup"><span data-stu-id="fc262-116">Represents an instance of an OSC provider.</span></span>  <br/> |
|[<span data-ttu-id="fc262-117">ISocialSession</span><span class="sxs-lookup"><span data-stu-id="fc262-117">ISocialSession</span></span>](isocialsessioniunknown.md) <br/> |<span data-ttu-id="fc262-118">表示与社交网络网站的连接。</span><span class="sxs-lookup"><span data-stu-id="fc262-118">Represents a connection to a social network site.</span></span>  <br/> |
|[<span data-ttu-id="fc262-119">ISocialSession2</span><span class="sxs-lookup"><span data-stu-id="fc262-119">ISocialSession2</span></span>](isocialsession2iunknown.md) <br/> |<span data-ttu-id="fc262-120">支持通过使用缓存凭据来同步活动、添加朋友、按需或混合同步, 或登录社交网络。</span><span class="sxs-lookup"><span data-stu-id="fc262-120">Supports synchronizing activities, adding friends, on-demand or hybrid synchronization of friends, or logging on to the social network by using cached credentials.</span></span>  <br/> |
   

