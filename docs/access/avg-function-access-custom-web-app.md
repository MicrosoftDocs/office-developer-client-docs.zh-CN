---
title: Avg 函数 (Access 自定义 web 应用程序)
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
localization_priority: Normal
ms.assetid: d432e823-a255-4860-9c8b-201b2e0476fd
description: 计算指定字段中包含的一组值的算术平均值。
ms.openlocfilehash: e67cde12e66f943d3b25fe9cb2fee4fe4aea760f
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33426721"
---
# <a name="avg-function-access-custom-web-app"></a>Avg 函数 (Access 自定义 web 应用程序)

计算指定字段中包含的一组值的算术平均值。
  
> [!IMPORTANT]
> Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。 
  
## <a name="syntax"></a>语法

 **Avg**(*NumericExpression*) 
  
**Avg**函数包含以下参数。 
  
|**参数**|**说明**|
|:-----|:-----|
|NumericExpression  <br/> |字符串表达式, 用于标识包含要求平均值的数值数据的字段, 或者是使用该字段中的数据执行计算的表达式。 *NumericExpression*中的操作数可以包括表字段、变量或函数 (可以是固有的或用户定义的函数, 但不能是其他 SQL 聚合函数) 的名称。  <br/> |
   
## <a name="remarks"></a>说明

使用 **Avg** 计算的平均值是算术平均值（值的总和除以值的数目）。例如，可以使用 **Avg** 计算运费的平均值。 
  
**Avg**函数不在计算中包含任何**Null**值。 
  

