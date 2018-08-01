---
title: 大于或等于 （访问自定义 web 应用程序）
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: cceb8dcb-5ce1-4c32-b057-6201b62a646f
description: 比较两个表达式为大于或等于。
ms.openlocfilehash: 425745d8634f92e3bcce3cbfcd7d11a890e3be4b
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773440"
---
# <a name="greater-than-or-equal-to-access-custom-web-app"></a><span data-ttu-id="5f945-103">大于或等于 （访问自定义 web 应用程序）</span><span class="sxs-lookup"><span data-stu-id="5f945-103">Greater Than or Equal To (Access custom web app)</span></span>

<span data-ttu-id="5f945-104">比较两个表达式为大于或等于。</span><span class="sxs-lookup"><span data-stu-id="5f945-104">Compares two expressions for greater than or equal.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="5f945-p101">Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。</span><span class="sxs-lookup"><span data-stu-id="5f945-p101">Microsoft no longer recommends creating and using Access web apps in SharePoint. As an alternative, consider using [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/) to build no-code business solutions for the web and mobile devices.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="5f945-107">语法</span><span class="sxs-lookup"><span data-stu-id="5f945-107">Syntax</span></span>

`>= (Greater Than or Equal To)`

<span data-ttu-id="5f945-108">*表达式*  \>=  *表达式*</span><span class="sxs-lookup"><span data-stu-id="5f945-108">*expression*  \>=  *expression*</span></span> 
  
<span data-ttu-id="5f945-109">*表达式* 是任何有效的表达式。</span><span class="sxs-lookup"><span data-stu-id="5f945-109">*expression*  Is any valid expression.</span></span> <span data-ttu-id="5f945-110">两个表达式都必须具有隐式转换的数据类型。</span><span class="sxs-lookup"><span data-stu-id="5f945-110">Both expressions must have implicitly convertible data types.</span></span> <span data-ttu-id="5f945-111">转换取决于数据类型优先级的规则。</span><span class="sxs-lookup"><span data-stu-id="5f945-111">The conversion depends on the rules of data type precedence.</span></span> 
  
## <a name="return-type"></a><span data-ttu-id="5f945-112">返回类型</span><span class="sxs-lookup"><span data-stu-id="5f945-112">Return Type</span></span>

<span data-ttu-id="5f945-113">**Boolean**</span><span class="sxs-lookup"><span data-stu-id="5f945-113">**Boolean**</span></span>
  
## <a name="remarks"></a><span data-ttu-id="5f945-114">说明</span><span class="sxs-lookup"><span data-stu-id="5f945-114">Remarks</span></span>

<span data-ttu-id="5f945-115">当比较非空表达式时，则结果为 TRUE，如果左侧的操作数的右侧操作数次; 比一个大于或等于值否则，则结果为 FALSE。</span><span class="sxs-lookup"><span data-stu-id="5f945-115">When you compare non-null expressions, the result is TRUE if the left operand has a greater or equal value than the right operand; otherwise, the result is FALSE.</span></span>
  

