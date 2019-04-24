---
title: Try_Convert 函数 (Access 自定义 web 应用程序)
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: ea514f19-4742-4eb4-823d-6f2494668106
description: 将值转换为指定的数据类型, 如果转换无效, 则返回 Null。
ms.openlocfilehash: 473d9063da46652afa88dc974cb4c4036e1c326c
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32304223"
---
# <a name="tryconvert-function-access-custom-web-app"></a><span data-ttu-id="92f1d-103">Try_Convert 函数 (Access 自定义 web 应用程序)</span><span class="sxs-lookup"><span data-stu-id="92f1d-103">Try_Convert Function (Access custom web app)</span></span>

<span data-ttu-id="92f1d-104">将值转换为指定的数据类型, 如果转换无效, 则返回 Null。</span><span class="sxs-lookup"><span data-stu-id="92f1d-104">Converts a value to a specified data type or returns Null if the conversion is not valid.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="92f1d-p101">Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。</span><span class="sxs-lookup"><span data-stu-id="92f1d-p101">Microsoft no longer recommends creating and using Access web apps in SharePoint. As an alternative, consider using [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/) to build no-code business solutions for the web and mobile devices.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="92f1d-107">语法</span><span class="sxs-lookup"><span data-stu-id="92f1d-107">Syntax</span></span>

 <span data-ttu-id="92f1d-108">**Try_Convert**(*DataType*、 *Expression*)</span><span class="sxs-lookup"><span data-stu-id="92f1d-108">**Try_Convert** (*DataType*, *Expression*)</span></span> 
  
<span data-ttu-id="92f1d-109">**Try_Convert**函数包含以下参数。</span><span class="sxs-lookup"><span data-stu-id="92f1d-109">The **Try_Convert** function contains the following arguments.</span></span> 
  
|<span data-ttu-id="92f1d-110">**参数名称**</span><span class="sxs-lookup"><span data-stu-id="92f1d-110">**Argument name**</span></span>|<span data-ttu-id="92f1d-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="92f1d-111">**Description**</span></span>|
|:-----|:-----|
| <span data-ttu-id="92f1d-112">*DataType*</span><span class="sxs-lookup"><span data-stu-id="92f1d-112">*DataType*</span></span>  <br/> |<span data-ttu-id="92f1d-113">要将*表达式*转换为的数据类型。</span><span class="sxs-lookup"><span data-stu-id="92f1d-113">The data type into which to convert  *Expression*  .</span></span>  <br/> |
| <span data-ttu-id="92f1d-114">*Expression*</span><span class="sxs-lookup"><span data-stu-id="92f1d-114">*Expression*</span></span>  <br/> |<span data-ttu-id="92f1d-115">要转换的值。</span><span class="sxs-lookup"><span data-stu-id="92f1d-115">The value to be converted.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="92f1d-116">注解</span><span class="sxs-lookup"><span data-stu-id="92f1d-116">Remarks</span></span>

 <span data-ttu-id="92f1d-117">**Try_Convert**获取传递给它的值, 并尝试将其转换为指定的*数据类型*。</span><span class="sxs-lookup"><span data-stu-id="92f1d-117">**Try_Convert** takes the value passed to it and tries to convert it to the specified  *DataType*  .</span></span> <span data-ttu-id="92f1d-118">如果转换成功, **Try_Convert**将以指定的*数据类型*返回值;如果发生错误, 则返回 null。</span><span class="sxs-lookup"><span data-stu-id="92f1d-118">If the conversion succeeds, **Try_Convert** returns the value as the specified  *DataType*  ; if an error occurs, null is returned.</span></span> <span data-ttu-id="92f1d-119">但是, 如果您请求显式不允许的转换, 则**Try_Convert**将失败并出现错误。</span><span class="sxs-lookup"><span data-stu-id="92f1d-119">However if you request a conversion that is explicitly not permitted, then **Try_Convert** fails with an error.</span></span> 
  

