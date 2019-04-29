---
title: BETWEEN (Access 自定义 web 应用)
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
localization_priority: Normal
ms.assetid: 9dcb32c6-ed9b-4a09-9e6a-48cc50063a6f
description: 指定要测试的范围。
ms.openlocfilehash: fd67d1163f6a39779e0202b5ca1ba998ba8650a7
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33429297"
---
# <a name="between-access-custom-web-app"></a>BETWEEN (Access 自定义 web 应用)

指定要测试的范围。
  
> [!IMPORTANT]
> Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。 
  
## <a name="syntax"></a>语法

 *test_expression* 不要**介于***begin_expression***,***end_expression* 
  
**Between**运算符包含下列参数。 
  
|**参数**|**必需**|**描述**|
|:-----|:-----|:-----|
| *test_expression*  <br/> |是  <br/> |要在*begin_expression*和*end_expression*定义的范围内进行测试的表达式。 必须与*begin_expression*和*end_expression*的数据类型相同。  <br/> |
| *NOT*  <br/> |否  <br/> |指定将谓词的结果取反。  <br/> |
| *begin_expression*  <br/> |是  <br/> |一个有效的表达式。 必须与*test_expression*和*end_expression*的数据类型相同。  <br/> |
| *end_expression*  <br/> |是  <br/> |一个有效的表达式。 必须与*test_expression*和*begin_expression*的数据类型相同。  <br/> |
| *AND*  <br/> |是  <br/> |指示*test_expression*应位于*begin_expression*和*end_expression*指示的范围内。  <br/> |
   
## <a name="result-type"></a>结果类型

 **Boolean**
  
## <a name="remarks"></a>说明

 **BETWEEN**如果*test_expression*的值大于或等于*begin_expression*的值, 小于或等于*end_expression*的值,**则返回 TRUE** 。 
  
 **NOT BETWEEN**如果*test_expression*的值小于*begin_expression*的值或大于*end_expression*的值,**则返回 TRUE** 。 
  
若要指定独占区域, 请使用大于号 (\>) 和小于运算符 (\<)。
  

