---
title: 表单管理器不支持的功能
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: b51e9e03-a333-4fdc-b6fe-87bd4e947b9f
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 86c91353b620482ca0862aa998aae1b3329cfc94
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19774617"
---
# <a name="capabilities-not-supported-by-form-managers"></a><span data-ttu-id="3cc6e-103">表单管理器不支持的功能</span><span class="sxs-lookup"><span data-stu-id="3cc6e-103">Capabilities Not Supported by Form Managers</span></span>

  
  
<span data-ttu-id="3cc6e-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="3cc6e-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="3cc6e-105">以下功能不受支持的默认窗体管理器出于性能原因，但可以支持的自定义窗体经理。</span><span class="sxs-lookup"><span data-stu-id="3cc6e-105">The following features are not supported by the default form manager for performance reasons but can be supported by custom form managers.</span></span>
  
- <span data-ttu-id="3cc6e-106">使窗体进行分组或整个表单库分类层次结构。</span><span class="sxs-lookup"><span data-stu-id="3cc6e-106">A hierarchy that enables forms to be grouped or categorized throughout a form library.</span></span> <span data-ttu-id="3cc6e-107">表单库是平面文件数据库的窗体。</span><span class="sxs-lookup"><span data-stu-id="3cc6e-107">A form library is a flat-file database of forms.</span></span>
    
- <span data-ttu-id="3cc6e-108">类别的窗体，邮件类或超类对应的访问控制。</span><span class="sxs-lookup"><span data-stu-id="3cc6e-108">Access control for categories of forms, corresponding to message classes or superclasses.</span></span>
    
- <span data-ttu-id="3cc6e-109">支持的单个窗体库中同一窗体的多个语言版本。</span><span class="sxs-lookup"><span data-stu-id="3cc6e-109">Support for multiple language versions of the same form in a single form library.</span></span>
    
<span data-ttu-id="3cc6e-110">这些是实现问题。</span><span class="sxs-lookup"><span data-stu-id="3cc6e-110">These are implementation issues.</span></span> <span data-ttu-id="3cc6e-111">没有任何限制阻止自定义窗体管理器实现这些功能。</span><span class="sxs-lookup"><span data-stu-id="3cc6e-111">There is nothing to prevent a custom form manager from implementing these features.</span></span>
  
<span data-ttu-id="3cc6e-112">MAPI 表单体系结构不支持同时运行的多个窗体管理器。</span><span class="sxs-lookup"><span data-stu-id="3cc6e-112">The MAPI form architecture does not support multiple form managers running concurrently.</span></span> <span data-ttu-id="3cc6e-113">尽管 MAPI 支持多个并发消息存储提供程序、 传输提供程序和通讯簿提供程序，支持单个窗体管理器。</span><span class="sxs-lookup"><span data-stu-id="3cc6e-113">Although MAPI supports multiple concurrent message store providers, transport providers, and address book providers, only a single form manager is supported.</span></span>
  
<span data-ttu-id="3cc6e-114">由于只有一个窗体管理器可能同时运行，如果您实现自定义窗体管理器，必须重新实现所需的默认窗体管理器从任何功能。</span><span class="sxs-lookup"><span data-stu-id="3cc6e-114">Because only one form manager may be running at once, if you implement a custom form manager you will have to re-implement any functionality from the default form manager that you need.</span></span> <span data-ttu-id="3cc6e-115">因为您的自定义窗体管理器将完全替换默认窗体管理器，默认窗体管理器的功能将不可用，除非他们在您的自定义窗体管理器重复。</span><span class="sxs-lookup"><span data-stu-id="3cc6e-115">Because your custom form manager will entirely replace the default form manager, capabilities of the default form manager will be unavailable unless they are duplicated in your custom form manager.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="3cc6e-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3cc6e-116">See also</span></span>



[<span data-ttu-id="3cc6e-117">MAPI 表单</span><span class="sxs-lookup"><span data-stu-id="3cc6e-117">MAPI Forms</span></span>](mapi-forms.md)

