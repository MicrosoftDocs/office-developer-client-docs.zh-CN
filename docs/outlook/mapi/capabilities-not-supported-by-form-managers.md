---
title: 表单管理器不支持的功能
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: b51e9e03-a333-4fdc-b6fe-87bd4e947b9f
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: e31eacaae54968fbdbd9fe0345130a8d09c3509f
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33419378"
---
# <a name="capabilities-not-supported-by-form-managers"></a><span data-ttu-id="612d5-103">表单管理器不支持的功能</span><span class="sxs-lookup"><span data-stu-id="612d5-103">Capabilities Not Supported by Form Managers</span></span>

  
  
<span data-ttu-id="612d5-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="612d5-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="612d5-105">由于性能原因, 默认表单管理器不支持以下功能, 但自定义表单管理器可能支持以下功能。</span><span class="sxs-lookup"><span data-stu-id="612d5-105">The following features are not supported by the default form manager for performance reasons but can be supported by custom form managers.</span></span>
  
- <span data-ttu-id="612d5-106">使表单能够在表单库中进行分组或分类的层次结构。</span><span class="sxs-lookup"><span data-stu-id="612d5-106">A hierarchy that enables forms to be grouped or categorized throughout a form library.</span></span> <span data-ttu-id="612d5-107">表单库是表单的平面文件数据库。</span><span class="sxs-lookup"><span data-stu-id="612d5-107">A form library is a flat-file database of forms.</span></span>
    
- <span data-ttu-id="612d5-108">与邮件类或超类对应的窗体类别的访问控制。</span><span class="sxs-lookup"><span data-stu-id="612d5-108">Access control for categories of forms, corresponding to message classes or superclasses.</span></span>
    
- <span data-ttu-id="612d5-109">在一个表单库中支持同一表单的多个语言版本。</span><span class="sxs-lookup"><span data-stu-id="612d5-109">Support for multiple language versions of the same form in a single form library.</span></span>
    
<span data-ttu-id="612d5-110">这些是实施问题。</span><span class="sxs-lookup"><span data-stu-id="612d5-110">These are implementation issues.</span></span> <span data-ttu-id="612d5-111">无需阻止自定义表单管理器实现这些功能。</span><span class="sxs-lookup"><span data-stu-id="612d5-111">There is nothing to prevent a custom form manager from implementing these features.</span></span>
  
<span data-ttu-id="612d5-112">MAPI 表单体系结构不支持同时运行多个表单管理器。</span><span class="sxs-lookup"><span data-stu-id="612d5-112">The MAPI form architecture does not support multiple form managers running concurrently.</span></span> <span data-ttu-id="612d5-113">虽然 MAPI 支持多个并发邮件存储提供程序、传输提供程序和通讯簿提供程序, 但只有一个表单管理器受支持。</span><span class="sxs-lookup"><span data-stu-id="612d5-113">Although MAPI supports multiple concurrent message store providers, transport providers, and address book providers, only a single form manager is supported.</span></span>
  
<span data-ttu-id="612d5-114">由于一次只能运行一个表单管理器, 因此如果实现自定义表单管理器, 则必须重新实现所需的默认表单管理器中的任何功能。</span><span class="sxs-lookup"><span data-stu-id="612d5-114">Because only one form manager may be running at once, if you implement a custom form manager you will have to re-implement any functionality from the default form manager that you need.</span></span> <span data-ttu-id="612d5-115">由于自定义表单管理器将完全替换默认表单管理器, 因此默认表单管理器的功能将不可用, 除非它们在自定义表单管理器中重复。</span><span class="sxs-lookup"><span data-stu-id="612d5-115">Because your custom form manager will entirely replace the default form manager, capabilities of the default form manager will be unavailable unless they are duplicated in your custom form manager.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="612d5-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="612d5-116">See also</span></span>



[<span data-ttu-id="612d5-117">MAPI 表单</span><span class="sxs-lookup"><span data-stu-id="612d5-117">MAPI Forms</span></span>](mapi-forms.md)

