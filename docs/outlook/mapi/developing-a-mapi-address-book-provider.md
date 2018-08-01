---
title: 开发 MAPI 通讯簿提供程序
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 821cc42d-eebb-4327-b2d4-594421a5c22c
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 03f53dbfbe57db76ee8ceefda3f6938301f70da8
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774777"
---
# <a name="developing-a-mapi-address-book-provider"></a><span data-ttu-id="da517-103">开发 MAPI 通讯簿提供程序</span><span class="sxs-lookup"><span data-stu-id="da517-103">Developing a MAPI Address Book Provider</span></span>

  
  
<span data-ttu-id="da517-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="da517-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="da517-105">通讯簿提供程序提供客户端应用程序，消息存储和传输提供程序，以及为 MAPI 的收件人信息。</span><span class="sxs-lookup"><span data-stu-id="da517-105">An address book provider supplies recipient information to client applications, to message store and transport providers, and to MAPI.</span></span> <span data-ttu-id="da517-106">到存储分栏称为容器层次结构组织收件人信息。</span><span class="sxs-lookup"><span data-stu-id="da517-106">Recipient information is organized hierarchically into storage compartments known as containers.</span></span> <span data-ttu-id="da517-107">配置文件中的每个通讯簿分配一个或更多首要，或父级到 MAPI 通讯簿，所有地址中的收件人信息集成视图的容器会话中书籍提供程序。</span><span class="sxs-lookup"><span data-stu-id="da517-107">Every address book in the profile contributes one or more top-level, or parent, containers to the MAPI address book, an integrated view of recipient information from all address book providers in a session.</span></span> <span data-ttu-id="da517-108">它是通过 MAPI 通讯簿的客户端和其他服务提供商访问通讯簿提供程序的数据。</span><span class="sxs-lookup"><span data-stu-id="da517-108">It is through the MAPI address book that clients and other service providers gain access to the data of an address book provider.</span></span>
  
<span data-ttu-id="da517-109">MAPI 生成通过集成的通讯簿：</span><span class="sxs-lookup"><span data-stu-id="da517-109">MAPI builds the integrated address book by:</span></span>
  
1. <span data-ttu-id="da517-110">检索每个通讯簿提供程序的顶级容器。</span><span class="sxs-lookup"><span data-stu-id="da517-110">Retrieving the top-level containers from each address book provider.</span></span>
    
2. <span data-ttu-id="da517-111">检索每个容器层次结构表。</span><span class="sxs-lookup"><span data-stu-id="da517-111">Retrieving each container's hierarchy table.</span></span> 
    
3. <span data-ttu-id="da517-112">将每个层次结构表复制到集成的层次结构表。</span><span class="sxs-lookup"><span data-stu-id="da517-112">Copying each hierarchy table into an integrated hierarchy table.</span></span> <span data-ttu-id="da517-113">它是公开给客户端集成的层次结构表。</span><span class="sxs-lookup"><span data-stu-id="da517-113">It is the integrated hierarchy table that is exposed to the client.</span></span> 
    
<span data-ttu-id="da517-114">MAPI 施加地址簿提供程序编写器几项的要求。</span><span class="sxs-lookup"><span data-stu-id="da517-114">MAPI imposes few requirements on address book provider writers.</span></span> <span data-ttu-id="da517-115">可能的功能的范围可以实现地址簿作者原样各种且灵活。</span><span class="sxs-lookup"><span data-stu-id="da517-115">The range of possible features you can implement as an address book writer is varied and flexible.</span></span> <span data-ttu-id="da517-116">例如，您的提供商可以限制为提供特定类型的收件人信息的只读视图或实现一组完整的功能，甚至可能允许客户端或提供程序，以使对收件人数据添加或修改并实施搜索条件，用于定义自定义视图。</span><span class="sxs-lookup"><span data-stu-id="da517-116">For example, your provider could be limited to supplying a read-only view of a particular type of recipient information or implement a full set of features, perhaps allowing clients or providers to make additions or modifications to the recipient data and to impose search criteria for defining customized views.</span></span> 
  
<span data-ttu-id="da517-117">提供程序的数据可以在文件、 数据库或远程服务器上本地驻留。</span><span class="sxs-lookup"><span data-stu-id="da517-117">Your provider's data can reside locally in a file or database or on a remote server.</span></span> <span data-ttu-id="da517-118">某些通讯簿提供程序是为了与特定的邮件系统，他人可以与任何邮件系统运行时与传输提供程序，紧密耦合工作。</span><span class="sxs-lookup"><span data-stu-id="da517-118">Some address book providers are meant to work with a particular messaging system, tightly coupled with a transport provider, while others can operate with any messaging system.</span></span>
  
<span data-ttu-id="da517-119">MAPI 定义一个特殊类型的名为个人通讯簿或 PAB、 的实现单个可修改容器并可容纳从其他容器以及创建直接信息复制的收件人信息的通讯簿提供程序。</span><span class="sxs-lookup"><span data-stu-id="da517-119">MAPI defines a special type of address book provider called a personal address book, or PAB, that implements a single modifiable container and can hold recipient information copied from other containers as well as information created directly.</span></span> <span data-ttu-id="da517-120">虽然任何通讯簿提供程序可以实现 PAB 并可以向一个配置文件添加多个 Pab，可以指定这些提供程序中的只有一个为 PAB 任何一个会话过程中运行。</span><span class="sxs-lookup"><span data-stu-id="da517-120">Although any address book provider can implement a PAB and multiple PABs can be added to a profile, only one of these providers can be designated to operate as the PAB during any one session.</span></span> 
  

