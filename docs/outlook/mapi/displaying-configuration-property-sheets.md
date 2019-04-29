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
# <a name="displaying-configuration-property-sheets"></a><span data-ttu-id="532d8-103">显示配置属性表</span><span class="sxs-lookup"><span data-stu-id="532d8-103">Displaying configuration property sheets</span></span>

<span data-ttu-id="532d8-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="532d8-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="532d8-105">传输提供程序使用[IMAPISupport::D oconfigpropsheet](imapisupport-doconfigpropsheet.md)方法来实现配置属性表。</span><span class="sxs-lookup"><span data-stu-id="532d8-105">Transport providers use the [IMAPISupport::DoConfigPropsheet](imapisupport-doconfigpropsheet.md) method to implement configuration property sheets.</span></span> <span data-ttu-id="532d8-106">调用**DoConfigPropSheet**时, 传输提供程序会将指针传递给一组属性, 并提供有关如何显示这些属性的信息。</span><span class="sxs-lookup"><span data-stu-id="532d8-106">When calling **DoConfigPropSheet**, the transport provider passes in a pointer to an array of properties along with information about how to display them.</span></span> <span data-ttu-id="532d8-107">然后, MAPI 通过标准对话框向用户显示属性。</span><span class="sxs-lookup"><span data-stu-id="532d8-107">MAPI then presents the properties to the user by means of a standard dialog box.</span></span> <span data-ttu-id="532d8-108">强烈建议您在实现传输提供程序时使用此属性表机制, 因为对一致接口的用户有益。</span><span class="sxs-lookup"><span data-stu-id="532d8-108">You are strongly encouraged to use this property sheet mechanism when implementing your transport provider due to the benefit to the user of a consistent interface.</span></span>
  
## <a name="transport-providers"></a><span data-ttu-id="532d8-109">传输提供程序</span><span class="sxs-lookup"><span data-stu-id="532d8-109">Transport providers</span></span>

<span data-ttu-id="532d8-110">传输提供程序可以使用[BuildDisplayTable](builddisplaytable.md)函数来简化显示表的构造, 以便与**DoConfigPropSheet**一起使用。</span><span class="sxs-lookup"><span data-stu-id="532d8-110">Transport providers can use the [BuildDisplayTable](builddisplaytable.md) function to simplify construction of a display table for use with **DoConfigPropSheet**.</span></span> <span data-ttu-id="532d8-111">传输提供程序还可以直接使用属性表 API。</span><span class="sxs-lookup"><span data-stu-id="532d8-111">Transport providers can also use the property sheet API directly.</span></span> <span data-ttu-id="532d8-112">若要缓冲对属性的更改, 传输提供程序可以使用[CreateIProp](createiprop.md)函数。</span><span class="sxs-lookup"><span data-stu-id="532d8-112">To buffer changes to the properties, transport providers can use the [CreateIProp](createiprop.md) function.</span></span> <span data-ttu-id="532d8-113">这简化了用户在用户修改存储在属性中的值时处理取消的操作。</span><span class="sxs-lookup"><span data-stu-id="532d8-113">This simplifies the handling of cancellations by the user while the user modifies the values stored in the properties.</span></span> <span data-ttu-id="532d8-114">如果需要, 传输提供程序还可以提供向导对话框来简化用户的配置任务。</span><span class="sxs-lookup"><span data-stu-id="532d8-114">If necessary, a transport provider can also provide a wizard dialog box to simplify configuration tasks for the user.</span></span> 
  

