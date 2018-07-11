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
# <a name="var-function-access-custom-web-app"></a>Var 函数 （访问自定义 web 应用程序）

返回总体样本抽样作为一组值包含在查询中的指定字段中的方差。
  
> [!IMPORTANT]
> [!重要信息] Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。 
  
## <a name="syntax"></a>语法

 **Var**(*NumericExpression*) 
  
**Var**函数包含以下参数。 
  
|**参数名称**|**说明**|
|:-----|:-----|
| *NumericExpression*  <br/> |标识包含要计算的数字数据或表达式的计算使用该字段中的数据的字段的文本表达式。 *NumericExpression*中可以包括表字段、 一个常量或函数 （这可能是固有或用户定义但不是其他 SQL 聚合函数） 的名称。  <br/> |
   
## <a name="remarks"></a>说明

 **Var**可用于仅限数字列。 空值将被忽略。 
  

