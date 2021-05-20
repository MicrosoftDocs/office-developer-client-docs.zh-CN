---
title: 编写自动化客户端
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: b8f9ac1a-b377-4f83-8fb6-ed85ab9053d0
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: f9ce3452bbc2d3297cc67168835a9387235746a8
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33439763"
---
# <a name="writing-an-automated-client"></a><span data-ttu-id="cc264-103">编写自动化客户端</span><span class="sxs-lookup"><span data-stu-id="cc264-103">Writing an Automated Client</span></span>

  
  
<span data-ttu-id="cc264-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="cc264-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="cc264-105">自动化客户端应用程序是无人参与运行的应用程序，不显示用户界面。</span><span class="sxs-lookup"><span data-stu-id="cc264-105">An automated client application is an application that runs unattended, displaying no user interface.</span></span>
  
 <span data-ttu-id="cc264-106">默认情况下，许多 MAPI 接口方法都显示用户界面。</span><span class="sxs-lookup"><span data-stu-id="cc264-106">By default, many MAPI interface methods show a user interface.</span></span> <span data-ttu-id="cc264-107">所有这些方法都有允许客户端允许或禁止此显示的标志。</span><span class="sxs-lookup"><span data-stu-id="cc264-107">All of these methods have flags that allow a client to either allow or suppress this display.</span></span> <span data-ttu-id="cc264-108">虽然 MAPI 期望服务提供商遵守这些标志，但有些提供程序并不总是符合这些预期要求。</span><span class="sxs-lookup"><span data-stu-id="cc264-108">Although MAPI expects service providers to honor these flags, there are some providers that do not always meet these expectations.</span></span> <span data-ttu-id="cc264-109">不遵守标志的合法原因是服务提供商依赖于不允许用户界面抑制的另一个服务。</span><span class="sxs-lookup"><span data-stu-id="cc264-109">A legitimate reason for not honoring the flags is the reliance of the service provider on another service that does not allow user interface suppression.</span></span> <span data-ttu-id="cc264-110">如果要开发自动化客户端，请仔细注意您使用的服务提供商及其配置方式。</span><span class="sxs-lookup"><span data-stu-id="cc264-110">If you are developing an automated client, pay careful attention to the service providers you are using and how they are configured.</span></span> <span data-ttu-id="cc264-111">不要假定用于禁止用户界面的所有调用都将成功。</span><span class="sxs-lookup"><span data-stu-id="cc264-111">Do not assume that all of your calls to suppress a user interface will be successful.</span></span> 
  
<span data-ttu-id="cc264-112">自动客户端必须具有必要的信息，以正确配置配置文件中每个邮件服务。</span><span class="sxs-lookup"><span data-stu-id="cc264-112">Automated clients must have the necessary information available for proper configuration of each of the message services in the profile.</span></span> <span data-ttu-id="cc264-113">有两种方法在登录时提供配置信息：</span><span class="sxs-lookup"><span data-stu-id="cc264-113">There are two ways to supply configuration information at logon time:</span></span>
  
- <span data-ttu-id="cc264-114">服务提供商可以从配置文件中检索信息。</span><span class="sxs-lookup"><span data-stu-id="cc264-114">The service provider can retrieve information from the profile.</span></span>
    
- <span data-ttu-id="cc264-115">服务提供商可以提示用户输入信息。</span><span class="sxs-lookup"><span data-stu-id="cc264-115">The service provider can prompt the user for information.</span></span> 
    
<span data-ttu-id="cc264-116">由于第二个选项对自动化客户端不可用，因此这些客户端必须使用第一个选项。</span><span class="sxs-lookup"><span data-stu-id="cc264-116">Since the second option is unavailable to automated clients, these clients must use the first option.</span></span> <span data-ttu-id="cc264-117">客户端必须仔细配置其配置文件，以确保此选项始终有效。</span><span class="sxs-lookup"><span data-stu-id="cc264-117">Clients must configure their profiles carefully to ensure that this option always works.</span></span>
  
<span data-ttu-id="cc264-118">自动客户端始终在 MAPILogonEx MAPI_NO_MAIL调用中设置 [mapILogonEx](mapilogonex.md) 标记以开始 MAPI 会话。</span><span class="sxs-lookup"><span data-stu-id="cc264-118">Automated clients always set the MAPI_NO_MAIL flag in the [MAPILogonEx](mapilogonex.md) function call to begin a MAPI session.</span></span> 
  

