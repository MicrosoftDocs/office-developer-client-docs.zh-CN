---
title: Sum 函数 (Access 自定义 web 应用程序)
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: c2345092-ba5f-4030-9070-391233e70f92
description: 返回表达式中所有值的总和。
ms.openlocfilehash: b0fed86469b32ddcc7f60a388f5d42c7bbd48b6c
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32304233"
---
# <a name="sum-function-access-custom-web-app"></a>Sum 函数 (Access 自定义 web 应用程序)

返回表达式中所有值的总和。
  
> [!IMPORTANT]
> Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。 
  
## <a name="syntax"></a>语法

 **Sum**(*NumericExpression*) 
  
**Sum**函数包含以下参数。 
  
|**参数名称**|**说明**|
|:-----|:-----|
| *NumericExpression*  <br/> |表达式, 用于标识包含要添加的数值数据的字段, 或者是使用该字段中的数据执行计算的表达式。 *NumericExpression*中的操作数可以包括表字段、常量或函数 (可以是固有的, 也可以是用户定义的, 但不能是其他 SQL 聚合函数) 的名称。  <br/> |
   
## <a name="remarks"></a>注解

**Sum**函数将忽略包含 Null 值的记录。 
  
**Sum**函数仅可用于数字列。 
  

