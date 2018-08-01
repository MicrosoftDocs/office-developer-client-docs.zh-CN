---
title: MAPI 提供程序与组件的交互
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 2c0e010b-0432-4ef7-a243-3a4b46f0a19d
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: cb0f8d5077b4851a50ceb8523943ae760a8ee5ce
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775967"
---
# <a name="interaction-of-mapi-providers-and-components"></a><span data-ttu-id="31a50-103">MAPI 提供程序与组件的交互</span><span class="sxs-lookup"><span data-stu-id="31a50-103">Interaction of MAPI Providers and Components</span></span>

  
  
<span data-ttu-id="31a50-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="31a50-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="31a50-105">任何类型的 MAPI 服务提供程序必须遵循某些准则以使用 MAPI 的其他组件。</span><span class="sxs-lookup"><span data-stu-id="31a50-105">MAPI service providers of any kind must follow certain guidelines to work with other MAPI components.</span></span> <span data-ttu-id="31a50-106">每个服务提供商必须：</span><span class="sxs-lookup"><span data-stu-id="31a50-106">Each service provider must:</span></span>
  
- <span data-ttu-id="31a50-107">用于初始化的适当的提供程序和登录对象。</span><span class="sxs-lookup"><span data-stu-id="31a50-107">Use the proper provider and logon objects for initialization.</span></span>
    
- <span data-ttu-id="31a50-108">消息系统初始化时返回调度表的提供程序入口点。</span><span class="sxs-lookup"><span data-stu-id="31a50-108">Return a dispatch table of provider entry points to the messaging system upon initialization.</span></span>
    
- <span data-ttu-id="31a50-109">注册 MAPI 状态表格行的服务提供商拥有每个资源，并在适当的时间调用[IMAPISupport::ModifyStatusRow](imapisupport-modifystatusrow.md)方法。</span><span class="sxs-lookup"><span data-stu-id="31a50-109">Register a MAPI status table row for each resource owned by the provider and call the [IMAPISupport::ModifyStatusRow](imapisupport-modifystatusrow.md) method at appropriate times.</span></span> 
    
- <span data-ttu-id="31a50-110">使用[IMAPISupport::NewUID](imapisupport-newuid.md)方法获取有效的唯一标识符 (Uid)。</span><span class="sxs-lookup"><span data-stu-id="31a50-110">Use the [IMAPISupport::NewUID](imapisupport-newuid.md) method to obtain valid unique identifiers (UIDs).</span></span> 
    
- <span data-ttu-id="31a50-111">支持将返回的对象的常见的 MAPI 接口。</span><span class="sxs-lookup"><span data-stu-id="31a50-111">Support the common MAPI interfaces on objects it returns.</span></span>
    
- <span data-ttu-id="31a50-112">使用 MAPI 内存分配函数，以返回到客户端应用程序的内存分配并释放内存分配由 MAPI 子系统的其他部分。</span><span class="sxs-lookup"><span data-stu-id="31a50-112">Use the MAPI memory allocation functions to allocate memory returned to client applications and to release memory allocated by other parts of the MAPI subsystem.</span></span>
    
- <span data-ttu-id="31a50-113">维护配置文件节，，如有必要，存储到基础邮件系统的凭据。</span><span class="sxs-lookup"><span data-stu-id="31a50-113">Maintain a profile section, if necessary, to store credentials to the underlying messaging system.</span></span>
    
- <span data-ttu-id="31a50-114">[IMAPISupport::RegisterPreprocessor](imapisupport-registerpreprocessor.md)方法用于注册任何消息预处理函数。</span><span class="sxs-lookup"><span data-stu-id="31a50-114">Use the [IMAPISupport::RegisterPreprocessor](imapisupport-registerpreprocessor.md) method to register any message preprocessing functions.</span></span> 
    
- <span data-ttu-id="31a50-115">包含适当的头文件 （包括 mapispi.h） 的定义常见常量、 结构、 接口和返回值。</span><span class="sxs-lookup"><span data-stu-id="31a50-115">Include the proper header files (including mapispi.h) that define common constants, structures, interfaces, and return values.</span></span>
    
- <span data-ttu-id="31a50-116">按照地址格式约定常见的地址类型。</span><span class="sxs-lookup"><span data-stu-id="31a50-116">Follow address format conventions for common address types.</span></span>
    

