---
title: 编写自动化客户端
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: b8f9ac1a-b377-4f83-8fb6-ed85ab9053d0
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: e5357c1e822dda35d3f38e00f91b58adbaf0ff9d
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779094"
---
# <a name="writing-an-automated-client"></a><span data-ttu-id="57b61-103">编写自动化客户端</span><span class="sxs-lookup"><span data-stu-id="57b61-103">Writing an Automated Client</span></span>

  
  
<span data-ttu-id="57b61-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="57b61-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="57b61-105">自动客户端应用程序是运行无人参与，不显示用户界面的应用程序。</span><span class="sxs-lookup"><span data-stu-id="57b61-105">An automated client application is an application that runs unattended, displaying no user interface.</span></span>
  
 <span data-ttu-id="57b61-106">默认情况下，许多 MAPI 接口方法显示用户界面。</span><span class="sxs-lookup"><span data-stu-id="57b61-106">By default, many MAPI interface methods show a user interface.</span></span> <span data-ttu-id="57b61-107">所有这些方法具有允许客户端，以允许或禁止此显示的标志。</span><span class="sxs-lookup"><span data-stu-id="57b61-107">All of these methods have flags that allow a client to either allow or suppress this display.</span></span> <span data-ttu-id="57b61-108">尽管 MAPI 预计服务提供商接受这些标志，有一些始终不满足这些期望的提供程序。</span><span class="sxs-lookup"><span data-stu-id="57b61-108">Although MAPI expects service providers to honor these flags, there are some providers that do not always meet these expectations.</span></span> <span data-ttu-id="57b61-109">不考虑标志的合法原因是服务提供程序，依赖于另一个不允许用户界面禁止显示的服务。</span><span class="sxs-lookup"><span data-stu-id="57b61-109">A legitimate reason for not honoring the flags is the reliance of the service provider on another service that does not allow user interface suppression.</span></span> <span data-ttu-id="57b61-110">如果要开发的自动客户端，请务必注意您使用的服务提供程序和配置方式。</span><span class="sxs-lookup"><span data-stu-id="57b61-110">If you are developing an automated client, pay careful attention to the service providers you are using and how they are configured.</span></span> <span data-ttu-id="57b61-111">不要假定所有呼叫禁止在用户界面将会成功。</span><span class="sxs-lookup"><span data-stu-id="57b61-111">Do not assume that all of your calls to suppress a user interface will be successful.</span></span> 
  
<span data-ttu-id="57b61-112">自动客户端必须具有所需的信息适用于每一个消息服务的正确配置配置文件中。</span><span class="sxs-lookup"><span data-stu-id="57b61-112">Automated clients must have the necessary information available for proper configuration of each of the message services in the profile.</span></span> <span data-ttu-id="57b61-113">有两种方式以提供登录时的配置信息：</span><span class="sxs-lookup"><span data-stu-id="57b61-113">There are two ways to supply configuration information at logon time:</span></span>
  
- <span data-ttu-id="57b61-114">服务提供商可以从配置文件中检索信息。</span><span class="sxs-lookup"><span data-stu-id="57b61-114">The service provider can retrieve information from the profile.</span></span>
    
- <span data-ttu-id="57b61-115">服务提供商可以提示用户输入的信息。</span><span class="sxs-lookup"><span data-stu-id="57b61-115">The service provider can prompt the user for information.</span></span> 
    
<span data-ttu-id="57b61-116">向自动化客户端，第二个选项不可用，因为这些客户端必须使用第一个选项。</span><span class="sxs-lookup"><span data-stu-id="57b61-116">Since the second option is unavailable to automated clients, these clients must use the first option.</span></span> <span data-ttu-id="57b61-117">客户端必须配置其配置文件仔细以确保始终此选项。</span><span class="sxs-lookup"><span data-stu-id="57b61-117">Clients must configure their profiles carefully to ensure that this option always works.</span></span>
  
<span data-ttu-id="57b61-118">自动客户端始终[MAPILogonEx](mapilogonex.md)函数调用开始 MAPI 会话中设置 MAPI_NO_MAIL 标志。</span><span class="sxs-lookup"><span data-stu-id="57b61-118">Automated clients always set the MAPI_NO_MAIL flag in the [MAPILogonEx](mapilogonex.md) function call to begin a MAPI session.</span></span> 
  

