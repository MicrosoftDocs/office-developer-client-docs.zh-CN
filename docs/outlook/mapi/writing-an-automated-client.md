---
title: 编写自动客户端
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: b8f9ac1a-b377-4f83-8fb6-ed85ab9053d0
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: f9ce3452bbc2d3297cc67168835a9387235746a8
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32325590"
---
# <a name="writing-an-automated-client"></a><span data-ttu-id="81211-103">编写自动客户端</span><span class="sxs-lookup"><span data-stu-id="81211-103">Writing an Automated Client</span></span>

  
  
<span data-ttu-id="81211-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="81211-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="81211-105">自动客户端应用程序是无人值守运行的应用程序, 不显示用户界面。</span><span class="sxs-lookup"><span data-stu-id="81211-105">An automated client application is an application that runs unattended, displaying no user interface.</span></span>
  
 <span data-ttu-id="81211-106">默认情况下, 许多 MAPI 接口方法显示一个用户界面。</span><span class="sxs-lookup"><span data-stu-id="81211-106">By default, many MAPI interface methods show a user interface.</span></span> <span data-ttu-id="81211-107">所有这些方法都有标志, 这些标志允许客户端允许或禁止显示此显示。</span><span class="sxs-lookup"><span data-stu-id="81211-107">All of these methods have flags that allow a client to either allow or suppress this display.</span></span> <span data-ttu-id="81211-108">虽然 MAPI 要求服务提供商服从这些标志, 但有些提供程序并不总是符合这些要求。</span><span class="sxs-lookup"><span data-stu-id="81211-108">Although MAPI expects service providers to honor these flags, there are some providers that do not always meet these expectations.</span></span> <span data-ttu-id="81211-109">不考虑这些标志的合理原因是, 服务提供商对另一项服务的依赖不允许用户界面抑制。</span><span class="sxs-lookup"><span data-stu-id="81211-109">A legitimate reason for not honoring the flags is the reliance of the service provider on another service that does not allow user interface suppression.</span></span> <span data-ttu-id="81211-110">如果要开发自动客户端, 请注意您正在使用的服务提供商以及它们的配置方式。</span><span class="sxs-lookup"><span data-stu-id="81211-110">If you are developing an automated client, pay careful attention to the service providers you are using and how they are configured.</span></span> <span data-ttu-id="81211-111">请勿假定所有调用以禁止用户界面都将成功。</span><span class="sxs-lookup"><span data-stu-id="81211-111">Do not assume that all of your calls to suppress a user interface will be successful.</span></span> 
  
<span data-ttu-id="81211-112">自动客户端必须具有可用于正确配置配置文件中的每个邮件服务的必要信息。</span><span class="sxs-lookup"><span data-stu-id="81211-112">Automated clients must have the necessary information available for proper configuration of each of the message services in the profile.</span></span> <span data-ttu-id="81211-113">登录时提供了两种提供配置信息的方法:</span><span class="sxs-lookup"><span data-stu-id="81211-113">There are two ways to supply configuration information at logon time:</span></span>
  
- <span data-ttu-id="81211-114">服务提供程序可以从配置文件中检索信息。</span><span class="sxs-lookup"><span data-stu-id="81211-114">The service provider can retrieve information from the profile.</span></span>
    
- <span data-ttu-id="81211-115">服务提供商可以提示用户输入信息。</span><span class="sxs-lookup"><span data-stu-id="81211-115">The service provider can prompt the user for information.</span></span> 
    
<span data-ttu-id="81211-116">由于第二个选项对自动客户端不可用, 因此这些客户端必须使用第一个选项。</span><span class="sxs-lookup"><span data-stu-id="81211-116">Since the second option is unavailable to automated clients, these clients must use the first option.</span></span> <span data-ttu-id="81211-117">客户端必须仔细配置其配置文件, 以确保此选项始终有效。</span><span class="sxs-lookup"><span data-stu-id="81211-117">Clients must configure their profiles carefully to ensure that this option always works.</span></span>
  
<span data-ttu-id="81211-118">自动客户端总是在[MAPILogonEx](mapilogonex.md)函数调用中设置 MAPI_NO_MAIL 标志以开始 MAPI 会话。</span><span class="sxs-lookup"><span data-stu-id="81211-118">Automated clients always set the MAPI_NO_MAIL flag in the [MAPILogonEx](mapilogonex.md) function call to begin a MAPI session.</span></span> 
  

