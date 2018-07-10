---
title: Sum 函数 （访问自定义 web 应用程序）
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: c2345092-ba5f-4030-9070-391233e70f92
description: 返回表达式中的所有值的总和。
ms.openlocfilehash: 98531a0487505c24ed62034b7c283b9765a3e7a7
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773619"
---
# <a name="sum-function-access-custom-web-app"></a><span data-ttu-id="cac42-103">Sum 函数 （访问自定义 web 应用程序）</span><span class="sxs-lookup"><span data-stu-id="cac42-103">Sum Function (Access custom web app)</span></span>

<span data-ttu-id="cac42-104">返回表达式中的所有值的总和。</span><span class="sxs-lookup"><span data-stu-id="cac42-104">Returns the sum of all the values in the expression.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="cac42-p101">Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/zh-cn/)，生成适用于 Web 和移动设备的无代码业务解决方案。</span><span class="sxs-lookup"><span data-stu-id="cac42-p101">Microsoft no longer recommends creating and using Access web apps in SharePoint. As an alternative, consider using [Microsoft PowerApps](https://powerapps.microsoft.com/zh-cn/) to build no-code business solutions for the web and mobile devices.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="cac42-107">语法</span><span class="sxs-lookup"><span data-stu-id="cac42-107">Syntax</span></span>

 <span data-ttu-id="cac42-108">**Sum**(*NumericExpression*)</span><span class="sxs-lookup"><span data-stu-id="cac42-108">**Sum** (*NumericExpression*)</span></span> 
  
<span data-ttu-id="cac42-109">**Sum**函数包含以下参数。</span><span class="sxs-lookup"><span data-stu-id="cac42-109">The **Sum** function contains the following argument.</span></span> 
  
|<span data-ttu-id="cac42-110">**参数名称**</span><span class="sxs-lookup"><span data-stu-id="cac42-110">**Argument name**</span></span>|<span data-ttu-id="cac42-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="cac42-111">**Description**</span></span>|
|:-----|:-----|
| <span data-ttu-id="cac42-112">*NumericExpression*</span><span class="sxs-lookup"><span data-stu-id="cac42-112">*NumericExpression*</span></span>  <br/> |<span data-ttu-id="cac42-113">表达式，用于标识包含您要添加的数字数据或表达式的计算使用该字段中的数据的字段。</span><span class="sxs-lookup"><span data-stu-id="cac42-113">An expression identifying the field that contains the numeric data you want to add or an expression that performs a calculation using the data in that field.</span></span> <span data-ttu-id="cac42-114">*NumericExpression*中可以包括表字段、 一个常量或函数 （这可能是固有或用户定义但不是其他 SQL 聚合函数） 的名称。</span><span class="sxs-lookup"><span data-stu-id="cac42-114">Operands in  *NumericExpression*  can include the name of a table field, a constant, or a function (which can be either intrinsic or user-defined but not one of the other SQL aggregate functions).</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="cac42-115">备注</span><span class="sxs-lookup"><span data-stu-id="cac42-115">Remarks</span></span>

<span data-ttu-id="cac42-116">**Sum**函数将忽略包含 Null 值的记录。</span><span class="sxs-lookup"><span data-stu-id="cac42-116">The **Sum** function ignores records that contain Null values.</span></span> 
  
<span data-ttu-id="cac42-117">仅可以与数字列使用**Sum**函数。</span><span class="sxs-lookup"><span data-stu-id="cac42-117">The **Sum** function can only be used with numeric columns.</span></span> 
  

