---
title: 'Try_Convert Function (Access 自定义 Web 应用) '
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: ea514f19-4742-4eb4-823d-6f2494668106
description: 将值转换为指定的数据类型或返回 Null（如果转换无效）。
ms.openlocfilehash: 473d9063da46652afa88dc974cb4c4036e1c326c
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33410894"
---
# <a name="try_convert-function-access-custom-web-app"></a><span data-ttu-id="2a929-103">Try_Convert Function (Access 自定义 Web 应用) </span><span class="sxs-lookup"><span data-stu-id="2a929-103">Try_Convert Function (Access custom web app)</span></span>

<span data-ttu-id="2a929-104">将值转换为指定的数据类型或返回 Null（如果转换无效）。</span><span class="sxs-lookup"><span data-stu-id="2a929-104">Converts a value to a specified data type or returns Null if the conversion is not valid.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="2a929-p101">Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。</span><span class="sxs-lookup"><span data-stu-id="2a929-p101">Microsoft no longer recommends creating and using Access web apps in SharePoint. As an alternative, consider using [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/) to build no-code business solutions for the web and mobile devices.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="2a929-107">语法</span><span class="sxs-lookup"><span data-stu-id="2a929-107">Syntax</span></span>

 <span data-ttu-id="2a929-108">**Try_Convert (\*\*\*数据类型，**表达式)\*</span><span class="sxs-lookup"><span data-stu-id="2a929-108">**Try_Convert** (*DataType*, *Expression*)</span></span> 
  
<span data-ttu-id="2a929-109">the **Try_Convert** function contains the following arguments.</span><span class="sxs-lookup"><span data-stu-id="2a929-109">The **Try_Convert** function contains the following arguments.</span></span> 
  
|<span data-ttu-id="2a929-110">**参数名称**</span><span class="sxs-lookup"><span data-stu-id="2a929-110">**Argument name**</span></span>|<span data-ttu-id="2a929-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="2a929-111">**Description**</span></span>|
|:-----|:-----|
| <span data-ttu-id="2a929-112">*DataType*</span><span class="sxs-lookup"><span data-stu-id="2a929-112">*DataType*</span></span>  <br/> |<span data-ttu-id="2a929-113">要将数据类型转换到的 *表达式 。*</span><span class="sxs-lookup"><span data-stu-id="2a929-113">The data type into which to convert  *Expression*  .</span></span>  <br/> |
| <span data-ttu-id="2a929-114">*Expression*</span><span class="sxs-lookup"><span data-stu-id="2a929-114">*Expression*</span></span>  <br/> |<span data-ttu-id="2a929-115">要转换的值。</span><span class="sxs-lookup"><span data-stu-id="2a929-115">The value to be converted.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="2a929-116">备注</span><span class="sxs-lookup"><span data-stu-id="2a929-116">Remarks</span></span>

 <span data-ttu-id="2a929-117">**Try_Convert** 传递给它的值，并尝试将其转换为指定的  *数据类型*  。</span><span class="sxs-lookup"><span data-stu-id="2a929-117">**Try_Convert** takes the value passed to it and tries to convert it to the specified  *DataType*  .</span></span> <span data-ttu-id="2a929-118">如果转换 **成功，则** Try_Convert  *DataType*  返回值;如果发生错误，则返回 null。</span><span class="sxs-lookup"><span data-stu-id="2a929-118">If the conversion succeeds, **Try_Convert** returns the value as the specified  *DataType*  ; if an error occurs, null is returned.</span></span> <span data-ttu-id="2a929-119">但是，如果您请求明确不允许的转换，则 **Try_Convert失败并** 出现错误。</span><span class="sxs-lookup"><span data-stu-id="2a929-119">However if you request a conversion that is explicitly not permitted, then **Try_Convert** fails with an error.</span></span> 
  

