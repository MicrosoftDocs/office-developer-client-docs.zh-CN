---
title: 关于错误值
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
f1_keywords:
- Vis_DSS.chm82251832
localization_priority: Normal
ms.assetid: 56430658-a798-c004-b4ba-363443f43ded
description: 错误值显示在含有该单元格的错误公式的单元格中。
ms.openlocfilehash: 5219becdd1af888e424a2fe33faa7df5a06f61fb
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33423865"
---
# <a name="about-error-values"></a>关于错误值

错误值显示在含有该单元格的错误公式的单元格中。
  
如果一个公式引用了含有错误值的单元格，该公式也会显示一个错误值。您可以使用 ISERR、ISERRNA、ISERROR 或 ISERRVALUE 函数来查看错误值。
  
**错误值**

||||
|:-----|:-----|:-----|
|**如果单元格显示** <br/> |**则公式包含** <br/> |**示例** <br/> |
| #DIV/0!  <br/> |被零除  <br/> |10/0  <br/> |
| #VALUE!  <br/> | 错误的参数或操作数类型  <br/> | 5 + "House"  <br/> |
| #REF!  <br/> | 指向不存在的单元格的引用  <br/> | 一个单元格引用另一个已不存在的单元格  <br/> |
| #NUM!  <br/> | 无效的数字  <br/> | 负数求平方根  <br/> |
| #N/A!  <br/> | 不是可用值  <br/> | NA( ) 函数  <br/> |
| #DIM!  <br/> | 超出维度范围的尺寸值 (有效的幂为整数-128 \<= n \<= 127)  <br/> 对一个尺寸值的不当操作  <br/> |1in ^ 100 \* 1in ^ 100 (结果是 1in ^ 200, 超出了维度范围)  <br/> 5.2cm^1.5（不是整数次幂）  <br/> |
   

