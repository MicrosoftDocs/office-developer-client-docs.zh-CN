---
title: Try_Convert 函数 （访问自定义 web 应用程序）
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: ea514f19-4742-4eb4-823d-6f2494668106
description: 将值转换为指定的数据类型，则返回 null 值，如果转换无效。
ms.openlocfilehash: ce942c1f444da7bfcbff76077a5a9d75dd611336
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773641"
---
# <a name="tryconvert-function-access-custom-web-app"></a><span data-ttu-id="837f2-103">Try_Convert 函数 （访问自定义 web 应用程序）</span><span class="sxs-lookup"><span data-stu-id="837f2-103">Try_Convert Function (Access custom web app)</span></span>

<span data-ttu-id="837f2-104">将值转换为指定的数据类型，则返回 null 值，如果转换无效。</span><span class="sxs-lookup"><span data-stu-id="837f2-104">Converts a value to a specified data type or returns Null if the conversion is not valid.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="837f2-p101">Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。</span><span class="sxs-lookup"><span data-stu-id="837f2-p101">Microsoft no longer recommends creating and using Access web apps in SharePoint. As an alternative, consider using [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/) to build no-code business solutions for the web and mobile devices.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="837f2-107">语法</span><span class="sxs-lookup"><span data-stu-id="837f2-107">Syntax</span></span>

 <span data-ttu-id="837f2-108">**Try_Convert**(*数据类型*，*表达式*)</span><span class="sxs-lookup"><span data-stu-id="837f2-108">**Try_Convert** (*DataType*, *Expression*)</span></span> 
  
<span data-ttu-id="837f2-109">**Try_Convert**函数包含以下参数。</span><span class="sxs-lookup"><span data-stu-id="837f2-109">The **Try_Convert** function contains the following arguments.</span></span> 
  
|<span data-ttu-id="837f2-110">**参数名称**</span><span class="sxs-lookup"><span data-stu-id="837f2-110">**Argument name**</span></span>|<span data-ttu-id="837f2-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="837f2-111">**Description**</span></span>|
|:-----|:-----|
| <span data-ttu-id="837f2-112">*数据类型*</span><span class="sxs-lookup"><span data-stu-id="837f2-112">*DataType*</span></span>  <br/> |<span data-ttu-id="837f2-113">到要将*表达式*转换为的数据类型。</span><span class="sxs-lookup"><span data-stu-id="837f2-113">The data type into which to convert  *Expression*  .</span></span>  <br/> |
| <span data-ttu-id="837f2-114">*Expression*</span><span class="sxs-lookup"><span data-stu-id="837f2-114">*Expression*</span></span>  <br/> |<span data-ttu-id="837f2-115">要转换的值。</span><span class="sxs-lookup"><span data-stu-id="837f2-115">The value to be converted.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="837f2-116">备注</span><span class="sxs-lookup"><span data-stu-id="837f2-116">Remarks</span></span>

 <span data-ttu-id="837f2-117">**Try_Convert**采用传递给它的值，并尝试将其转换为指定的*数据类型*。</span><span class="sxs-lookup"><span data-stu-id="837f2-117">**Try_Convert** takes the value passed to it and tries to convert it to the specified  *DataType*  .</span></span> <span data-ttu-id="837f2-118">如果转换成功，则**Try_Convert**返回值为指定*数据类型*;如果出现错误，则返回 null。</span><span class="sxs-lookup"><span data-stu-id="837f2-118">If the conversion succeeds, **Try_Convert** returns the value as the specified  *DataType*  ; if an error occurs, null is returned.</span></span> <span data-ttu-id="837f2-119">但是如果请求明确不允许的转换，然后**Try_Convert**失败并出现错误。</span><span class="sxs-lookup"><span data-stu-id="837f2-119">However if you request a conversion that is explicitly not permitted, then **Try_Convert** fails with an error.</span></span> 
  

