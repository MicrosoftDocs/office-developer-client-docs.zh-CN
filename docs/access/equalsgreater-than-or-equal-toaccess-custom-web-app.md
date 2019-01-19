---
title: 大于或等于（Access 自定义 Web 应用）
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: reference
ms.assetid: cceb8dcb-5ce1-4c32-b057-6201b62a646f
description: 比较两个大于或等于的表达式。
localization_priority: Priority
ms.openlocfilehash: 76472544be950c68f3b5d42fe13b3040e9268f48
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28709255"
---
# <a name="greater-than-or-equal-to-access-custom-web-app"></a><span data-ttu-id="59f61-103">大于或等于（Access 自定义 Web 应用）</span><span class="sxs-lookup"><span data-stu-id="59f61-103">Greater Than or Equal To (Access custom web app)</span></span>

<span data-ttu-id="59f61-104">比较两个大于或等于的表达式。</span><span class="sxs-lookup"><span data-stu-id="59f61-104">Compares two expressions for greater than or equal.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="59f61-p101">Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/zh-CN/)，生成适用于 Web 和移动设备的无代码业务解决方案。</span><span class="sxs-lookup"><span data-stu-id="59f61-p101">Microsoft no longer recommends creating and using Access web apps in SharePoint. As an alternative, consider using [Microsoft PowerApps](https://powerapps.microsoft.com/zh-CN/) to build no-code business solutions for the web and mobile devices.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="59f61-107">语法</span><span class="sxs-lookup"><span data-stu-id="59f61-107">Syntax</span></span>

`>= (Greater Than or Equal To)`

<span data-ttu-id="59f61-108">*expression*  \>=  *expression*</span><span class="sxs-lookup"><span data-stu-id="59f61-108">*expression*  \>=  *expression*</span></span> 
  
<span data-ttu-id="59f61-109">*expression* 表示任何有效的表达式。</span><span class="sxs-lookup"><span data-stu-id="59f61-109">*expression*  Is any valid expression.</span></span> <span data-ttu-id="59f61-110">两个表达式必须具有隐式可转换的数据类型。</span><span class="sxs-lookup"><span data-stu-id="59f61-110">Both expressions must have implicitly convertible data types.</span></span> <span data-ttu-id="59f61-111">转换取决于数据类型优先级的规则。</span><span class="sxs-lookup"><span data-stu-id="59f61-111">The conversion depends on the rules of data type precedence.</span></span> 
  
## <a name="return-type"></a><span data-ttu-id="59f61-112">返回类型</span><span class="sxs-lookup"><span data-stu-id="59f61-112">Return Type</span></span>

<span data-ttu-id="59f61-113">**Boolean**</span><span class="sxs-lookup"><span data-stu-id="59f61-113">**Boolean**</span></span>
  
## <a name="remarks"></a><span data-ttu-id="59f61-114">备注</span><span class="sxs-lookup"><span data-stu-id="59f61-114">Remarks</span></span>

<span data-ttu-id="59f61-115">比较非 Null 表达式时，如果左操作数大于或等于右操作数，结果为 TRUE；否则结果为 FALSE。</span><span class="sxs-lookup"><span data-stu-id="59f61-115">When you compare non-null expressions, the result is TRUE if the left operand has a greater or equal value than the right operand; otherwise, the result is FALSE.</span></span>
  

