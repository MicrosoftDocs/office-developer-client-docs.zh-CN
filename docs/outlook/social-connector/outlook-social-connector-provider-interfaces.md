---
title: Outlook Social Connector 提供程序接口
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 8f92b2c7-9f47-4c84-874b-fec1a2a5b555
description: Outlook Social Connector (OSC) 是由 Office 客户端应用程序共享 Office 功能，用于连接到社交和业务网络以便用户可以保持联系他们的网络中的人员，而不必离开办公室。
ms.openlocfilehash: bc393f32e563bbbef70538ea00cd92cf7f96729c
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779325"
---
# <a name="outlook-social-connector-provider-interfaces"></a><span data-ttu-id="23a0e-103">Outlook Social Connector 提供程序接口</span><span class="sxs-lookup"><span data-stu-id="23a0e-103">Outlook Social Connector provider interfaces</span></span>

<span data-ttu-id="23a0e-104">Outlook Social Connector (OSC) 是由 Office 客户端应用程序共享 Office 功能，用于连接到社交和业务网络以便用户可以保持联系他们的网络中的人员，而不必离开办公室。</span><span class="sxs-lookup"><span data-stu-id="23a0e-104">The Outlook Social Connector (OSC) is an Office feature shared by Office client applications that connects to social and business networks so users can stay in touch with the people in their networks without leaving Office.</span></span> 
  
<span data-ttu-id="23a0e-105">OSC 提供程序组件对象模型 (COM) 允许 OSC 访问一种方式独立于每个社交网络的 Api 中的社交网络数据的 DLL。</span><span class="sxs-lookup"><span data-stu-id="23a0e-105">An OSC provider is a Component Object Model (COM) DLL that allows the OSC to access social network data in a way that is independent of the APIs of each social network.</span></span> <span data-ttu-id="23a0e-106">下表列出在 OSC 提供程序扩展性的接口。</span><span class="sxs-lookup"><span data-stu-id="23a0e-106">The following table lists the interfaces in OSC provider extensibility.</span></span> <span data-ttu-id="23a0e-107">OSC 提供程序必须实现四个与 OSC 进行通信的五个接口： [ISocialPerson](isocialpersoniunknown.md)、 [ISocialProfile](isocialprofileisocialperson.md)、 [ISocialProvider](isocialprovideriunknown.md)和[ISocialSession](isocialsessioniunknown.md)。</span><span class="sxs-lookup"><span data-stu-id="23a0e-107">An OSC provider must implement four of the five interfaces to communicate with the OSC: [ISocialPerson](isocialpersoniunknown.md), [ISocialProfile](isocialprofileisocialperson.md), [ISocialProvider](isocialprovideriunknown.md), and [ISocialSession](isocialsessioniunknown.md).</span></span> <span data-ttu-id="23a0e-108">提供程序如果 OSC 提供程序支持同步活动，按需或朋友缓存登录凭据和日志记录已使用混合同步缓存凭据或关注人员的功能，应实现[ISocialSession2](isocialsession2iunknown.md)、 以及。</span><span class="sxs-lookup"><span data-stu-id="23a0e-108">If the OSC provider supports synchronizing activities, on-demand or hybrid synchronization of friends, caching logon credentials and logging on using cached credentials, or the ability to follow a person, the provider should implement [ISocialSession2](isocialsession2iunknown.md), as well.</span></span>
  
|<span data-ttu-id="23a0e-109">**名称**</span><span class="sxs-lookup"><span data-stu-id="23a0e-109">**Name**</span></span>|<span data-ttu-id="23a0e-110">**说明**</span><span class="sxs-lookup"><span data-stu-id="23a0e-110">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="23a0e-111">ISocialPerson</span><span class="sxs-lookup"><span data-stu-id="23a0e-111">ISocialPerson</span></span>](isocialpersoniunknown.md) <br/> |<span data-ttu-id="23a0e-112">表示在社交网络的人员。</span><span class="sxs-lookup"><span data-stu-id="23a0e-112">Represents a person on the social network.</span></span>  <br/> |
|[<span data-ttu-id="23a0e-113">ISocialProfile</span><span class="sxs-lookup"><span data-stu-id="23a0e-113">ISocialProfile</span></span>](isocialprofileisocialperson.md) <br/> |<span data-ttu-id="23a0e-114">代表登录用户。</span><span class="sxs-lookup"><span data-stu-id="23a0e-114">Represents the logged-on user.</span></span>  <br/> |
|[<span data-ttu-id="23a0e-115">ISocialProvider</span><span class="sxs-lookup"><span data-stu-id="23a0e-115">ISocialProvider</span></span>](isocialprovideriunknown.md) <br/> |<span data-ttu-id="23a0e-116">表示 OSC 提供程序的实例。</span><span class="sxs-lookup"><span data-stu-id="23a0e-116">Represents an instance of an OSC provider.</span></span>  <br/> |
|[<span data-ttu-id="23a0e-117">ISocialSession</span><span class="sxs-lookup"><span data-stu-id="23a0e-117">ISocialSession</span></span>](isocialsessioniunknown.md) <br/> |<span data-ttu-id="23a0e-118">代表与社交网络站点的连接。</span><span class="sxs-lookup"><span data-stu-id="23a0e-118">Represents a connection to a social network site.</span></span>  <br/> |
|[<span data-ttu-id="23a0e-119">ISocialSession2</span><span class="sxs-lookup"><span data-stu-id="23a0e-119">ISocialSession2</span></span>](isocialsession2iunknown.md) <br/> |<span data-ttu-id="23a0e-120">支持同步活动，添加朋友点播或混合同步朋友或登录到使用社交网络缓存凭据。</span><span class="sxs-lookup"><span data-stu-id="23a0e-120">Supports synchronizing activities, adding friends, on-demand or hybrid synchronization of friends, or logging on to the social network by using cached credentials.</span></span>  <br/> |
   

