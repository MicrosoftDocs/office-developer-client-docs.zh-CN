---
title: Avg 函数 （访问自定义 web 应用程序）
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
localization_priority: Normal
ms.assetid: d432e823-a255-4860-9c8b-201b2e0476fd
description: 计算的一组指定的字段中包含的值的算术平均值。
ms.openlocfilehash: afe832a51fc9cd3b224087a0b06fe539f6a7004b
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773438"
---
# <a name="avg-function-access-custom-web-app"></a>Avg 函数 （访问自定义 web 应用程序）

计算的一组指定的字段中包含的值的算术平均值。
  
> [!IMPORTANT]
> [!重要信息] Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。 
  
## <a name="syntax"></a>语法

 **平均**(*NumericExpression*) 
  
**Avg**函数包含以下参数。 
  
|**参数**|**说明**|
|:-----|:-----|
|NumericExpression  <br/> |标识包含数值数据的字段的字符串表达式要平均值或表达式的计算使用该字段中的数据。 *NumericExpression*中可以包括表字段、 变量或函数 （这可能是固有或用户定义但不是其他 SQL 聚合函数） 的名称。  <br/> |
   
## <a name="remarks"></a>备注

计算**平均**的平均值是算术平均值 （值的总和的值的数量的比率）。 您可以使用**Avg**，例如，计算平均运货成本。 
  
**Avg**函数不包括**Null**值的计算中。 
  

