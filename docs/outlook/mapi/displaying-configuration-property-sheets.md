---
title: 显示配置属性表
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: c9386b98-615f-488c-8212-11d9abebbdcf
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: a796f458e9d30206dc4c6feb37cbdb1e6b6a704b
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33421310"
---
# <a name="displaying-configuration-property-sheets"></a><span data-ttu-id="9cbe2-103">显示配置属性表</span><span class="sxs-lookup"><span data-stu-id="9cbe2-103">Displaying configuration property sheets</span></span>

<span data-ttu-id="9cbe2-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="9cbe2-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="9cbe2-105">传输提供程序使用 [IMAPISupport：:D oConfigPropsheet](imapisupport-doconfigpropsheet.md) 方法实现配置属性表。</span><span class="sxs-lookup"><span data-stu-id="9cbe2-105">Transport providers use the [IMAPISupport::DoConfigPropsheet](imapisupport-doconfigpropsheet.md) method to implement configuration property sheets.</span></span> <span data-ttu-id="9cbe2-106">调用 **DoConfigPropSheet** 时，传输提供程序会传递一个指向属性数组的指针，以及有关如何显示这些属性的信息。</span><span class="sxs-lookup"><span data-stu-id="9cbe2-106">When calling **DoConfigPropSheet**, the transport provider passes in a pointer to an array of properties along with information about how to display them.</span></span> <span data-ttu-id="9cbe2-107">然后，MAPI 通过标准对话框向用户显示属性。</span><span class="sxs-lookup"><span data-stu-id="9cbe2-107">MAPI then presents the properties to the user by means of a standard dialog box.</span></span> <span data-ttu-id="9cbe2-108">强烈建议在使用传输提供程序属性表此传输提供程序，因为一致的接口对用户的好处。</span><span class="sxs-lookup"><span data-stu-id="9cbe2-108">You are strongly encouraged to use this property sheet mechanism when implementing your transport provider due to the benefit to the user of a consistent interface.</span></span>
  
## <a name="transport-providers"></a><span data-ttu-id="9cbe2-109">传输提供程序</span><span class="sxs-lookup"><span data-stu-id="9cbe2-109">Transport providers</span></span>

<span data-ttu-id="9cbe2-110">传输提供程序可以使用 [BuildDisplayTable](builddisplaytable.md) 函数来简化用于 **DoConfigPropSheet 的显示表的构造**。</span><span class="sxs-lookup"><span data-stu-id="9cbe2-110">Transport providers can use the [BuildDisplayTable](builddisplaytable.md) function to simplify construction of a display table for use with **DoConfigPropSheet**.</span></span> <span data-ttu-id="9cbe2-111">传输提供程序也可以直接属性表 API。</span><span class="sxs-lookup"><span data-stu-id="9cbe2-111">Transport providers can also use the property sheet API directly.</span></span> <span data-ttu-id="9cbe2-112">若要缓冲对属性的更改，传输提供程序可以使用 [CreateIProp](createiprop.md) 函数。</span><span class="sxs-lookup"><span data-stu-id="9cbe2-112">To buffer changes to the properties, transport providers can use the [CreateIProp](createiprop.md) function.</span></span> <span data-ttu-id="9cbe2-113">这简化了用户在修改属性中存储的值时对取消的处理。</span><span class="sxs-lookup"><span data-stu-id="9cbe2-113">This simplifies the handling of cancellations by the user while the user modifies the values stored in the properties.</span></span> <span data-ttu-id="9cbe2-114">如有必要，传输提供程序还可以提供一个向导对话框来简化用户的配置任务。</span><span class="sxs-lookup"><span data-stu-id="9cbe2-114">If necessary, a transport provider can also provide a wizard dialog box to simplify configuration tasks for the user.</span></span> 
  

