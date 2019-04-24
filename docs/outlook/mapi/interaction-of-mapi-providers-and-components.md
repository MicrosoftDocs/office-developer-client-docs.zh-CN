---
title: MAPI 提供程序和组件的交互
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 2c0e010b-0432-4ef7-a243-3a4b46f0a19d
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: b88eafcc1ca6be98c5c1e9418072a5cb35f43345
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32332170"
---
# <a name="interaction-of-mapi-providers-and-components"></a><span data-ttu-id="85952-103">MAPI 提供程序和组件的交互</span><span class="sxs-lookup"><span data-stu-id="85952-103">Interaction of MAPI Providers and Components</span></span>

  
  
<span data-ttu-id="85952-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="85952-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="85952-105">任何种类的 MAPI 服务提供程序都必须遵循特定的准则来使用其他 MAPI 组件。</span><span class="sxs-lookup"><span data-stu-id="85952-105">MAPI service providers of any kind must follow certain guidelines to work with other MAPI components.</span></span> <span data-ttu-id="85952-106">每个服务提供程序都必须:</span><span class="sxs-lookup"><span data-stu-id="85952-106">Each service provider must:</span></span>
  
- <span data-ttu-id="85952-107">使用正确的提供程序和登录对象进行初始化。</span><span class="sxs-lookup"><span data-stu-id="85952-107">Use the proper provider and logon objects for initialization.</span></span>
    
- <span data-ttu-id="85952-108">初始化时, 向邮件系统返回提供程序入口点的派送表。</span><span class="sxs-lookup"><span data-stu-id="85952-108">Return a dispatch table of provider entry points to the messaging system upon initialization.</span></span>
    
- <span data-ttu-id="85952-109">为提供程序拥有的每个资源注册 MAPI 状态表行, 并在适当的时候调用[IMAPISupport:: ModifyStatusRow](imapisupport-modifystatusrow.md)方法。</span><span class="sxs-lookup"><span data-stu-id="85952-109">Register a MAPI status table row for each resource owned by the provider and call the [IMAPISupport::ModifyStatusRow](imapisupport-modifystatusrow.md) method at appropriate times.</span></span> 
    
- <span data-ttu-id="85952-110">使用[IMAPISupport:: NewUID](imapisupport-newuid.md)方法获取有效的唯一标识符 (uid)。</span><span class="sxs-lookup"><span data-stu-id="85952-110">Use the [IMAPISupport::NewUID](imapisupport-newuid.md) method to obtain valid unique identifiers (UIDs).</span></span> 
    
- <span data-ttu-id="85952-111">支持它返回的对象上的常见 MAPI 接口。</span><span class="sxs-lookup"><span data-stu-id="85952-111">Support the common MAPI interfaces on objects it returns.</span></span>
    
- <span data-ttu-id="85952-112">使用 mapi 内存分配函数分配返回给客户端应用程序的内存, 并释放由 MAPI 子系统的其他部分分配的内存。</span><span class="sxs-lookup"><span data-stu-id="85952-112">Use the MAPI memory allocation functions to allocate memory returned to client applications and to release memory allocated by other parts of the MAPI subsystem.</span></span>
    
- <span data-ttu-id="85952-113">如果需要, 请维护配置文件部分, 以将凭据存储到基础邮件系统中。</span><span class="sxs-lookup"><span data-stu-id="85952-113">Maintain a profile section, if necessary, to store credentials to the underlying messaging system.</span></span>
    
- <span data-ttu-id="85952-114">使用[IMAPISupport:: RegisterPreprocessor](imapisupport-registerpreprocessor.md)方法可注册任何邮件预处理函数。</span><span class="sxs-lookup"><span data-stu-id="85952-114">Use the [IMAPISupport::RegisterPreprocessor](imapisupport-registerpreprocessor.md) method to register any message preprocessing functions.</span></span> 
    
- <span data-ttu-id="85952-115">包括用于定义常见常量、结构、接口和返回值的适当头文件 (包括 mapispi)。</span><span class="sxs-lookup"><span data-stu-id="85952-115">Include the proper header files (including mapispi.h) that define common constants, structures, interfaces, and return values.</span></span>
    
- <span data-ttu-id="85952-116">遵循常用地址类型的地址格式约定。</span><span class="sxs-lookup"><span data-stu-id="85952-116">Follow address format conventions for common address types.</span></span>
    

