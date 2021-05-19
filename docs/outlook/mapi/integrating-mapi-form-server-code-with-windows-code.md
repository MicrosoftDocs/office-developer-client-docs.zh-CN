---
title: 将 MAPI 表单服务器代码与 Windows 代码集成
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 47ec3e97-ad2b-43ea-842a-b2a0675eef48
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 33b205c0ac5caf5fc049a0732cd219aa2c321326
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32332177"
---
# <a name="integrating-mapi-form-server-code-with-windows-code"></a><span data-ttu-id="8fbfc-103">将 MAPI 表单服务器代码与 Windows 代码集成</span><span class="sxs-lookup"><span data-stu-id="8fbfc-103">Integrating MAPI Form Server Code with Windows Code</span></span>

  
  
<span data-ttu-id="8fbfc-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="8fbfc-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="8fbfc-105">回想一下，您的表单服务器是 Win32 应用程序。</span><span class="sxs-lookup"><span data-stu-id="8fbfc-105">Recall that your form server is a Win32 application.</span></span> <span data-ttu-id="8fbfc-106">因此，有些任务与将表单服务器加载到内存中并完全退出有关。</span><span class="sxs-lookup"><span data-stu-id="8fbfc-106">As such, there are some tasks related to loading your form server into memory and exiting cleanly.</span></span> <span data-ttu-id="8fbfc-107">与Windows一样，表单服务器的入口点是 **WinMain** 函数。</span><span class="sxs-lookup"><span data-stu-id="8fbfc-107">Like all Windows applications, the entry point for your form server is the **WinMain** function.</span></span> <span data-ttu-id="8fbfc-108">此函数是执行以下任务的适当位置：</span><span class="sxs-lookup"><span data-stu-id="8fbfc-108">This function is the appropriate place to perform the following tasks:</span></span> 
  
- <span data-ttu-id="8fbfc-109">创建和注册窗口类，以便表单服务器可以与其他 OLE 组件交互。</span><span class="sxs-lookup"><span data-stu-id="8fbfc-109">Creating and registering a window class so that your form server can interact with other OLE components.</span></span>
    
- <span data-ttu-id="8fbfc-110">为表单对象的用户界面创建和注册窗口类。</span><span class="sxs-lookup"><span data-stu-id="8fbfc-110">Creating and registering a window class or classes for your form objects' user interfaces.</span></span>
    
- <span data-ttu-id="8fbfc-111">调用 [MAPIInitialize](mapiinitialize.md) 函数。</span><span class="sxs-lookup"><span data-stu-id="8fbfc-111">Calling the [MAPIInitialize](mapiinitialize.md) function.</span></span> <span data-ttu-id="8fbfc-112">**MAPIInitialize** 也处理所需的 OLE 初始化。</span><span class="sxs-lookup"><span data-stu-id="8fbfc-112">**MAPIInitialize** handles the required OLE initialization for you, as well.</span></span> <span data-ttu-id="8fbfc-113">每个表单服务器实例必须完成一次此操作。</span><span class="sxs-lookup"><span data-stu-id="8fbfc-113">This must be done once per instance of your form server.</span></span> 
    
- <span data-ttu-id="8fbfc-114">使用表单服务器的类标识符的字符串表示形式注册全局 atom (CLSID) 。</span><span class="sxs-lookup"><span data-stu-id="8fbfc-114">Registering a global atom with a string representation of the form server's class identifier (CLSID).</span></span> <span data-ttu-id="8fbfc-115">此 atom 应在窗体服务器的生命周期内存在。</span><span class="sxs-lookup"><span data-stu-id="8fbfc-115">This atom should exist for the lifetime of the form server.</span></span>
    
- <span data-ttu-id="8fbfc-116">调用 OLE 函数 [CoRegisterClassObject](https://msdn.microsoft.com/library/ms693407.aspx) 以使用 OLE 注册表单服务器的类工厂。</span><span class="sxs-lookup"><span data-stu-id="8fbfc-116">Calling the OLE function [CoRegisterClassObject](https://msdn.microsoft.com/library/ms693407.aspx) to register your form server's class factory with OLE.</span></span> 
    
- <span data-ttu-id="8fbfc-117">创建主窗口以接收邮件。</span><span class="sxs-lookup"><span data-stu-id="8fbfc-117">Creating a main window to receive messages.</span></span> <span data-ttu-id="8fbfc-118">此窗口可能不需要可见，因为用户将与与单个表单对象关联的特定窗口交互。</span><span class="sxs-lookup"><span data-stu-id="8fbfc-118">This window probably does not need to be visible because the user will be interacting with the specific windows associated with individual form objects.</span></span> <span data-ttu-id="8fbfc-119">但是，在开发过程中，主窗口可以是调试表单服务器的输出或控制的方便位置。</span><span class="sxs-lookup"><span data-stu-id="8fbfc-119">However, during development, the main window can be a convenient place for debugging output or control of your form server.</span></span>
    
- <span data-ttu-id="8fbfc-120">创建在窗体服务器生存期内运行的消息循环，将窗口消息转换和调度到活动窗体对象。</span><span class="sxs-lookup"><span data-stu-id="8fbfc-120">Creating a message loop that runs for the lifetime of the form server, translating and dispatching windows messages to active form objects.</span></span>
    
<span data-ttu-id="8fbfc-121">当表单服务器退出时，它应执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="8fbfc-121">When your form server exits, it should perform the following tasks:</span></span>
  
- <span data-ttu-id="8fbfc-122">调用 OLE 函数 [CoRevokeClassObject](https://msdn.microsoft.com/library/ms688650%28VS.85%29.aspx) 以撤消邮件类的 OLE 注册。</span><span class="sxs-lookup"><span data-stu-id="8fbfc-122">Call the OLE function [CoRevokeClassObject](https://msdn.microsoft.com/library/ms688650%28VS.85%29.aspx) to revoke your message class's OLE registration.</span></span> 
    
- <span data-ttu-id="8fbfc-123">调用 **MAPIUninitialize** 以正确关闭表单服务器与 MAPI 的连接。</span><span class="sxs-lookup"><span data-stu-id="8fbfc-123">Call **MAPIUninitialize** to properly close the form server's connection to MAPI.</span></span> 
    
- <span data-ttu-id="8fbfc-124">删除包含类标识符的字符串表示的全局 atom。</span><span class="sxs-lookup"><span data-stu-id="8fbfc-124">Delete the global atom that contains the string representation of the class identifier.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="8fbfc-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8fbfc-125">See also</span></span>



[<span data-ttu-id="8fbfc-126">编写表单服务器代码</span><span class="sxs-lookup"><span data-stu-id="8fbfc-126">Writing Form Server Code</span></span>](writing-form-server-code.md)

