---
title: 之间 （访问自定义 web 应用程序）
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
localization_priority: Normal
ms.assetid: 9dcb32c6-ed9b-4a09-9e6a-48cc50063a6f
description: 指定要测试的范围。
ms.openlocfilehash: 0ef3384d6a29826968220f8d6cfc0d2f85e1131c
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773449"
---
# <a name="between-access-custom-web-app"></a>之间 （访问自定义 web 应用程序）

指定要测试的范围。
  
> [!IMPORTANT]
> Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。 
  
## <a name="syntax"></a>语法

 *test_expression* [NOT]**BETWEEN***begin_expression***AND***end_expression* 
  
**Between**运算符包含下列参数。 
  
|**参数**|**必需**|**说明**|
|:-----|:-----|:-----|
| *test_expression*  <br/> |可访问  <br/> |要测试定义*begin_expression*和*end_expression*的范围中的表达式。 必须为*begin_expression*和*end_expression*同一字段数据类型。  <br/> |
| *NOT*  <br/> |否  <br/> |指定否定谓词的结果。  <br/> |
| *begin_expression*  <br/> |可访问  <br/> |一个有效表达式。 必须为*test_expression*和*end_expression*同一字段数据类型。  <br/> |
| *end_expression*  <br/> |可访问  <br/> |一个有效表达式。 必须为*test_expression*和*begin_expression*同一字段数据类型。  <br/> |
| *AND*  <br/> |可访问  <br/> |指示*test_expression*应由*begin_expression*和*end_expression*指示范围内。  <br/> |
   
## <a name="result-type"></a>结果类型

 **Boolean**
  
## <a name="remarks"></a>说明

 **BETWEEN**返回**TRUE** ，如果*test_expression*值大于或等于*begin_expression*值且小于或等于*end_expression*的值。 
  
 **之间不**返回**TRUE** ，如果*test_expression*的值小于 value *begin_expression*或大于*end_expression*的值。 
  
要指定排除范围，请使用大于比 (\>) 且小于运算符 (\<)。
  

