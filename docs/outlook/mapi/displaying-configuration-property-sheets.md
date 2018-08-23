---
title: 显示配置属性表
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: c9386b98-615f-488c-8212-11d9abebbdcf
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: fa48e97ed25fe1175ffd3a92ac961dcf5bde50b4
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22588354"
---
# <a name="displaying-configuration-property-sheets"></a><span data-ttu-id="d1e09-103">显示配置属性表</span><span class="sxs-lookup"><span data-stu-id="d1e09-103">Displaying configuration property sheets</span></span>

<span data-ttu-id="d1e09-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d1e09-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="d1e09-105">传输提供程序使用[IMAPISupport::DoConfigPropsheet](imapisupport-doconfigpropsheet.md)方法实现配置属性表。</span><span class="sxs-lookup"><span data-stu-id="d1e09-105">Transport providers use the [IMAPISupport::DoConfigPropsheet](imapisupport-doconfigpropsheet.md) method to implement configuration property sheets.</span></span> <span data-ttu-id="d1e09-106">调用**DoConfigPropSheet**时, 传输提供程序将一个指针传递到数组属性以及有关如何将其显示的信息。</span><span class="sxs-lookup"><span data-stu-id="d1e09-106">When calling **DoConfigPropSheet**, the transport provider passes in a pointer to an array of properties along with information about how to display them.</span></span> <span data-ttu-id="d1e09-107">MAPI 然后会向用户的属性通过标准的对话框中显示。</span><span class="sxs-lookup"><span data-stu-id="d1e09-107">MAPI then presents the properties to the user by means of a standard dialog box.</span></span> <span data-ttu-id="d1e09-108">要实现的用户的一致的界面为带来的好处由于您传输提供程序时使用此属性表机制强烈建议。</span><span class="sxs-lookup"><span data-stu-id="d1e09-108">You are strongly encouraged to use this property sheet mechanism when implementing your transport provider due to the benefit to the user of a consistent interface.</span></span>
  
## <a name="transport-providers"></a><span data-ttu-id="d1e09-109">传输提供程序</span><span class="sxs-lookup"><span data-stu-id="d1e09-109">Transport providers</span></span>

<span data-ttu-id="d1e09-110">传输提供程序可以使用[BuildDisplayTable](builddisplaytable.md)函数来简化**DoConfigPropSheet**用于显示表的构造。</span><span class="sxs-lookup"><span data-stu-id="d1e09-110">Transport providers can use the [BuildDisplayTable](builddisplaytable.md) function to simplify construction of a display table for use with **DoConfigPropSheet**.</span></span> <span data-ttu-id="d1e09-111">传输提供程序也可以直接使用的属性表 API。</span><span class="sxs-lookup"><span data-stu-id="d1e09-111">Transport providers can also use the property sheet API directly.</span></span> <span data-ttu-id="d1e09-112">若要缓冲区对属性的更改，传输提供程序可以使用[CreateIProp](createiprop.md)函数。</span><span class="sxs-lookup"><span data-stu-id="d1e09-112">To buffer changes to the properties, transport providers can use the [CreateIProp](createiprop.md) function.</span></span> <span data-ttu-id="d1e09-113">这样可简化处理的取消由用户时用户修改的属性中存储的值。</span><span class="sxs-lookup"><span data-stu-id="d1e09-113">This simplifies the handling of cancellations by the user while the user modifies the values stored in the properties.</span></span> <span data-ttu-id="d1e09-114">如果需要，传输提供程序还可以提供一个向导对话框框以简化用户的配置任务。</span><span class="sxs-lookup"><span data-stu-id="d1e09-114">If necessary, a transport provider can also provide a wizard dialog box to simplify configuration tasks for the user.</span></span> 
  

