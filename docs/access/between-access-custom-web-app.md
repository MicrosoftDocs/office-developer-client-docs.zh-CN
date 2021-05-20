---
title: 'Between (Access 自定义 Web 应用) '
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
# <a name="between-access-custom-web-app"></a>Between (Access 自定义 Web 应用) 

指定要测试的范围。
  
> [!IMPORTANT]
> Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。 
  
## <a name="syntax"></a>语法

 *test_expression* [ NOT ] **between begin_expression**  **AND end_expression**  
  
Between 运算符包含下列参数。 
  
|**参数**|**必需**|**描述**|
|:-----|:-----|:-----|
| *test_expression*  <br/> |是  <br/> |在由 begin_expression 和 end_expression 定义的范围内 *测试的表达式*。 必须与 数据类型 和  *begin_expression*  *end_expression*  相同。  <br/> |
| *NOT*  <br/> |否  <br/> |指定要否定谓词的结果。  <br/> |
| *begin_expression*  <br/> |是  <br/> |一个有效的表达式。 必须与 数据类型 和  *test_expression end_expression*  *相同*  。  <br/> |
| *end_expression*  <br/> |是  <br/> |一个有效的表达式。 必须与 数据类型 和  *test_expression begin_expression*  *相同*  。  <br/> |
| AND  <br/> |是  <br/> |指示 *test_expression* 值应位于由 begin_expression 和 *end_expression* *指示的end_expression。*  <br/> |
   
## <a name="result-type"></a>结果类型

 **Boolean**
  
## <a name="remarks"></a>说明

 **BETWEEN** 返回 **TRUE** test_expression *值大于或* 等于 *begin_expression* 小于或等于值 end_expression *。* 
  
 **NOT BETWEEN** 返回 **TRUE** test_expression *值小于**begin_expression值或* 大于值 *end_expression* 。 
  
若要指定独占区域，请使用大于 (\>) 运算符 () 。 \<
  

