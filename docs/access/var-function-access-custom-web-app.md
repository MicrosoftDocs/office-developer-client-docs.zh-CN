---
title: Var 函数 (Access 自定义 web 应用程序)
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: cb2aace1-fa2d-480e-bfc7-44ae399943f5
description: 返回总体样本的统计方差, 表示为查询中指定字段中包含的一组值。
ms.openlocfilehash: 80cea512b0386d9b0461c927675ae51be3e0dcda
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32304198"
---
# <a name="var-function-access-custom-web-app"></a>Var 函数 (Access 自定义 web 应用程序)

返回总体样本的统计方差, 表示为查询中指定字段中包含的一组值。
  
> [!IMPORTANT]
> Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。 
  
## <a name="syntax"></a>语法

 **Var**(*NumericExpression*) 
  
**Var**函数包含以下参数。 
  
|**参数名称**|**说明**|
|:-----|:-----|
| *NumericExpression*  <br/> |文本表达式, 用于标识包含要计算的数值数据的字段, 或者是使用该字段中的数据执行计算的表达式。 *NumericExpression*中的操作数可以包括表字段、常量或函数 (可以是固有的, 也可以是用户定义的, 但不能是其他 SQL 聚合函数) 的名称。  <br/> |
   
## <a name="remarks"></a>注解

 **Var**仅可用于数字列。 Null 值将被忽略。 
  

