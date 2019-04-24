---
title: 开发 MAPI 通讯簿提供程序
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 821cc42d-eebb-4327-b2d4-594421a5c22c
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 1db3ce53a1da60d946e52a03369c10547676277f
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32316700"
---
# <a name="developing-a-mapi-address-book-provider"></a><span data-ttu-id="22914-103">开发 MAPI 通讯簿提供程序</span><span class="sxs-lookup"><span data-stu-id="22914-103">Developing a MAPI Address Book Provider</span></span>

  
  
<span data-ttu-id="22914-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="22914-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="22914-105">通讯簿提供程序向客户端应用程序、邮件存储和传输提供程序以及 MAPI 提供收件人信息。</span><span class="sxs-lookup"><span data-stu-id="22914-105">An address book provider supplies recipient information to client applications, to message store and transport providers, and to MAPI.</span></span> <span data-ttu-id="22914-106">收件人信息按层次结构组织到称为容器的存储隔离舱中。</span><span class="sxs-lookup"><span data-stu-id="22914-106">Recipient information is organized hierarchically into storage compartments known as containers.</span></span> <span data-ttu-id="22914-107">配置文件中的每个通讯簿都会将一个或多个顶级容器 (或父容器) 分配给 MAPI 通讯簿, 这是来自会话中所有通讯簿提供程序的收件人信息的集成视图。</span><span class="sxs-lookup"><span data-stu-id="22914-107">Every address book in the profile contributes one or more top-level, or parent, containers to the MAPI address book, an integrated view of recipient information from all address book providers in a session.</span></span> <span data-ttu-id="22914-108">通过 MAPI 通讯簿, 客户端和其他服务提供商即可访问通讯簿提供程序的数据。</span><span class="sxs-lookup"><span data-stu-id="22914-108">It is through the MAPI address book that clients and other service providers gain access to the data of an address book provider.</span></span>
  
<span data-ttu-id="22914-109">MAPI 通过以下方式构建集成的通讯簿:</span><span class="sxs-lookup"><span data-stu-id="22914-109">MAPI builds the integrated address book by:</span></span>
  
1. <span data-ttu-id="22914-110">从每个通讯簿提供程序检索顶级容器。</span><span class="sxs-lookup"><span data-stu-id="22914-110">Retrieving the top-level containers from each address book provider.</span></span>
    
2. <span data-ttu-id="22914-111">检索每个容器的层次结构表。</span><span class="sxs-lookup"><span data-stu-id="22914-111">Retrieving each container's hierarchy table.</span></span> 
    
3. <span data-ttu-id="22914-112">将每个层次结构表复制到一个集成的层次结构表中。</span><span class="sxs-lookup"><span data-stu-id="22914-112">Copying each hierarchy table into an integrated hierarchy table.</span></span> <span data-ttu-id="22914-113">它是向客户端公开的集成层次结构表。</span><span class="sxs-lookup"><span data-stu-id="22914-113">It is the integrated hierarchy table that is exposed to the client.</span></span> 
    
<span data-ttu-id="22914-114">MAPI 对通讯簿提供程序编写者施加的要求很少。</span><span class="sxs-lookup"><span data-stu-id="22914-114">MAPI imposes few requirements on address book provider writers.</span></span> <span data-ttu-id="22914-115">作为通讯簿编写者而可以实现的可能功能的范围是不同且灵活的。</span><span class="sxs-lookup"><span data-stu-id="22914-115">The range of possible features you can implement as an address book writer is varied and flexible.</span></span> <span data-ttu-id="22914-116">例如, 您的提供程序可以限制为提供特定类型的收件人信息的只读视图, 也可以实现一组完整的功能, 从而允许客户端或提供程序对收件人数据进行添加或修改并强制实施用于定义自定义视图的搜索条件。</span><span class="sxs-lookup"><span data-stu-id="22914-116">For example, your provider could be limited to supplying a read-only view of a particular type of recipient information or implement a full set of features, perhaps allowing clients or providers to make additions or modifications to the recipient data and to impose search criteria for defining customized views.</span></span> 
  
<span data-ttu-id="22914-117">提供程序的数据可以驻留在本地的文件或数据库中或远程服务器上。</span><span class="sxs-lookup"><span data-stu-id="22914-117">Your provider's data can reside locally in a file or database or on a remote server.</span></span> <span data-ttu-id="22914-118">有些通讯簿提供程序用于处理特定的邮件系统, 与传输提供程序紧密结合, 而其他人可以在任何邮件系统上运行。</span><span class="sxs-lookup"><span data-stu-id="22914-118">Some address book providers are meant to work with a particular messaging system, tightly coupled with a transport provider, while others can operate with any messaging system.</span></span>
  
<span data-ttu-id="22914-119">MAPI 定义一种特殊类型的通讯簿提供程序, 称为个人通讯簿或 PAB, 它实现单个可修改容器, 并可以保留从其他容器复制的收件人信息以及直接创建的信息。</span><span class="sxs-lookup"><span data-stu-id="22914-119">MAPI defines a special type of address book provider called a personal address book, or PAB, that implements a single modifiable container and can hold recipient information copied from other containers as well as information created directly.</span></span> <span data-ttu-id="22914-120">尽管任何通讯簿提供程序都可以实现 PAB, 并且可以将多个 PABs 添加到配置文件中, 但只有其中一个提供程序可以指定为在任何一个会话过程中作为 PAB 运行。</span><span class="sxs-lookup"><span data-stu-id="22914-120">Although any address book provider can implement a PAB and multiple PABs can be added to a profile, only one of these providers can be designated to operate as the PAB during any one session.</span></span> 
  

