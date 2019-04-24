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
# <a name="integrating-mapi-form-server-code-with-windows-code"></a><span data-ttu-id="cead9-103">将 MAPI 表单服务器代码与 Windows 代码集成</span><span class="sxs-lookup"><span data-stu-id="cead9-103">Integrating MAPI Form Server Code with Windows Code</span></span>

  
  
<span data-ttu-id="cead9-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="cead9-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="cead9-105">请记住, 您的表单服务器是 Win32 应用程序。</span><span class="sxs-lookup"><span data-stu-id="cead9-105">Recall that your form server is a Win32 application.</span></span> <span data-ttu-id="cead9-106">因此, 存在一些与将表单服务器加载到内存中并完全退出相关的任务。</span><span class="sxs-lookup"><span data-stu-id="cead9-106">As such, there are some tasks related to loading your form server into memory and exiting cleanly.</span></span> <span data-ttu-id="cead9-107">与所有 Windows 应用程序一样, 表单服务器的入口点是**WinMain**函数。</span><span class="sxs-lookup"><span data-stu-id="cead9-107">Like all Windows applications, the entry point for your form server is the **WinMain** function.</span></span> <span data-ttu-id="cead9-108">此函数是执行以下任务的适当位置:</span><span class="sxs-lookup"><span data-stu-id="cead9-108">This function is the appropriate place to perform the following tasks:</span></span> 
  
- <span data-ttu-id="cead9-109">创建并注册一个 window 类, 以便您的表单服务器可以与其他 OLE 组件进行交互。</span><span class="sxs-lookup"><span data-stu-id="cead9-109">Creating and registering a window class so that your form server can interact with other OLE components.</span></span>
    
- <span data-ttu-id="cead9-110">为表单对象的用户界面创建和注册一个窗口类或类。</span><span class="sxs-lookup"><span data-stu-id="cead9-110">Creating and registering a window class or classes for your form objects' user interfaces.</span></span>
    
- <span data-ttu-id="cead9-111">调用[MAPIInitialize](mapiinitialize.md)函数。</span><span class="sxs-lookup"><span data-stu-id="cead9-111">Calling the [MAPIInitialize](mapiinitialize.md) function.</span></span> <span data-ttu-id="cead9-112">**MAPIInitialize**也为您处理所需的 OLE 初始化。</span><span class="sxs-lookup"><span data-stu-id="cead9-112">**MAPIInitialize** handles the required OLE initialization for you, as well.</span></span> <span data-ttu-id="cead9-113">必须为每个表单服务器实例执行一次此操作。</span><span class="sxs-lookup"><span data-stu-id="cead9-113">This must be done once per instance of your form server.</span></span> 
    
- <span data-ttu-id="cead9-114">使用表单服务器的类标识符 (CLSID) 的字符串表示形式注册全局 atom。</span><span class="sxs-lookup"><span data-stu-id="cead9-114">Registering a global atom with a string representation of the form server's class identifier (CLSID).</span></span> <span data-ttu-id="cead9-115">此 atom 应存在于表单服务器的生存期中。</span><span class="sxs-lookup"><span data-stu-id="cead9-115">This atom should exist for the lifetime of the form server.</span></span>
    
- <span data-ttu-id="cead9-116">调用 ole 函数[CoRegisterClassObject](https://msdn.microsoft.com/library/ms693407.aspx)以使用 ole 注册窗体服务器的类工厂。</span><span class="sxs-lookup"><span data-stu-id="cead9-116">Calling the OLE function [CoRegisterClassObject](https://msdn.microsoft.com/library/ms693407.aspx) to register your form server's class factory with OLE.</span></span> 
    
- <span data-ttu-id="cead9-117">创建用于接收邮件的主窗口。</span><span class="sxs-lookup"><span data-stu-id="cead9-117">Creating a main window to receive messages.</span></span> <span data-ttu-id="cead9-118">此窗口可能不需要显示, 因为用户将与与各个表单对象相关联的特定窗口进行交互。</span><span class="sxs-lookup"><span data-stu-id="cead9-118">This window probably does not need to be visible because the user will be interacting with the specific windows associated with individual form objects.</span></span> <span data-ttu-id="cead9-119">但是, 在开发过程中, 主窗口可用作调试表单服务器的输出或控制的便利位置。</span><span class="sxs-lookup"><span data-stu-id="cead9-119">However, during development, the main window can be a convenient place for debugging output or control of your form server.</span></span>
    
- <span data-ttu-id="cead9-120">创建在表单服务器的生存期内运行的邮件循环, 将 windows 消息转换并调度到活动的窗体对象。</span><span class="sxs-lookup"><span data-stu-id="cead9-120">Creating a message loop that runs for the lifetime of the form server, translating and dispatching windows messages to active form objects.</span></span>
    
<span data-ttu-id="cead9-121">当表单服务器退出时, 应执行以下任务:</span><span class="sxs-lookup"><span data-stu-id="cead9-121">When your form server exits, it should perform the following tasks:</span></span>
  
- <span data-ttu-id="cead9-122">调用 OLE 函数[CoRevokeClassObject](https://msdn.microsoft.com/library/ms688650%28VS.85%29.aspx)以撤消您的邮件类的 OLE 注册。</span><span class="sxs-lookup"><span data-stu-id="cead9-122">Call the OLE function [CoRevokeClassObject](https://msdn.microsoft.com/library/ms688650%28VS.85%29.aspx) to revoke your message class's OLE registration.</span></span> 
    
- <span data-ttu-id="cead9-123">调用**MAPIUninitialize**以正确关闭表单服务器与 MAPI 的连接。</span><span class="sxs-lookup"><span data-stu-id="cead9-123">Call **MAPIUninitialize** to properly close the form server's connection to MAPI.</span></span> 
    
- <span data-ttu-id="cead9-124">删除包含类标识符的字符串表示形式的全局 atom。</span><span class="sxs-lookup"><span data-stu-id="cead9-124">Delete the global atom that contains the string representation of the class identifier.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="cead9-125">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cead9-125">See also</span></span>



[<span data-ttu-id="cead9-126">编写表单服务器代码</span><span class="sxs-lookup"><span data-stu-id="cead9-126">Writing Form Server Code</span></span>](writing-form-server-code.md)

