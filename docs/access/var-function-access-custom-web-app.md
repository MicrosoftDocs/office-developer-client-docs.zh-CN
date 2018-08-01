---
title: Var 函数 （访问自定义 web 应用程序）
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: cb2aace1-fa2d-480e-bfc7-44ae399943f5
description: 返回总体样本抽样作为一组值包含在查询中的指定字段中的方差。
ms.openlocfilehash: 9937f1985c0a7df5eb06977333ab889947891380
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773631"
---
# <a name="var-function-access-custom-web-app"></a><span data-ttu-id="fdcc9-103">Var 函数 （访问自定义 web 应用程序）</span><span class="sxs-lookup"><span data-stu-id="fdcc9-103">Var Function (Access custom web app)</span></span>

<span data-ttu-id="fdcc9-104">返回总体样本抽样作为一组值包含在查询中的指定字段中的方差。</span><span class="sxs-lookup"><span data-stu-id="fdcc9-104">Returns the statistical variance for a population sample represented as a set of values contained in a specified field in a query.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="fdcc9-p101">Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。</span><span class="sxs-lookup"><span data-stu-id="fdcc9-p101">Microsoft no longer recommends creating and using Access web apps in SharePoint. As an alternative, consider using [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/) to build no-code business solutions for the web and mobile devices.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="fdcc9-107">语法</span><span class="sxs-lookup"><span data-stu-id="fdcc9-107">Syntax</span></span>

 <span data-ttu-id="fdcc9-108">**Var**(*NumericExpression*)</span><span class="sxs-lookup"><span data-stu-id="fdcc9-108">**Var** (*NumericExpression*)</span></span> 
  
<span data-ttu-id="fdcc9-109">**Var**函数包含以下参数。</span><span class="sxs-lookup"><span data-stu-id="fdcc9-109">The **Var** function contains the following argument.</span></span> 
  
|<span data-ttu-id="fdcc9-110">**参数名称**</span><span class="sxs-lookup"><span data-stu-id="fdcc9-110">**Argument name**</span></span>|<span data-ttu-id="fdcc9-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="fdcc9-111">**Description**</span></span>|
|:-----|:-----|
| <span data-ttu-id="fdcc9-112">*NumericExpression*</span><span class="sxs-lookup"><span data-stu-id="fdcc9-112">*NumericExpression*</span></span>  <br/> |<span data-ttu-id="fdcc9-113">标识包含要计算的数字数据或表达式的计算使用该字段中的数据的字段的文本表达式。</span><span class="sxs-lookup"><span data-stu-id="fdcc9-113">A text expression identifying the field that contains the numeric data you want to evaluate or an expression that performs a calculation using the data in that field.</span></span> <span data-ttu-id="fdcc9-114">*NumericExpression*中可以包括表字段、 一个常量或函数 （这可能是固有或用户定义但不是其他 SQL 聚合函数） 的名称。</span><span class="sxs-lookup"><span data-stu-id="fdcc9-114">Operands in  *NumericExpression*  can include the name of a table field, a constant, or a function (which can be either intrinsic or user-defined but not one of the other SQL aggregate functions).</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="fdcc9-115">说明</span><span class="sxs-lookup"><span data-stu-id="fdcc9-115">Remarks</span></span>

 <span data-ttu-id="fdcc9-116">**Var**可用于仅限数字列。</span><span class="sxs-lookup"><span data-stu-id="fdcc9-116">**Var** can be used with numeric columns only.</span></span> <span data-ttu-id="fdcc9-117">空值将被忽略。</span><span class="sxs-lookup"><span data-stu-id="fdcc9-117">Null values are ignored.</span></span> 
  

