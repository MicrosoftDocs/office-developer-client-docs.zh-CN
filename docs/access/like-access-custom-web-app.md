---
title: 'Like (Access custom web app) '
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: decdd8fc-2184-4d97-b918-3ef6ab1ab40b
description: 确定特定字符字符串是否与指定的模式匹配。 模式可以包括常规字符和通配符。 在模式匹配期间，常规字符必须与字符字符串中指定的字符完全匹配。 但是，通配符可以与字符串的任意片段匹配。 使用通配符使 LIKE 运算符比使用 = 和 ！= 字符串比较运算符更灵活。
ms.openlocfilehash: 02d1e4f8fc61335e828a1f77579c14b1c7577485
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33406113"
---
# <a name="like-access-custom-web-app"></a>Like (Access custom web app) 

确定特定字符字符串是否与指定的模式匹配。 模式可以包括常规字符和通配符。 在模式匹配期间，常规字符必须与字符字符串中指定的字符完全匹配。 但是，通配符可以与字符串的任意片段匹配。 使用通配符使 **LIKE** 运算符比使用 = 和 ！= 字符串比较运算符更灵活。 
  
> [!IMPORTANT]
> Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。 
  
## <a name="syntax"></a>语法

 *表达式*  [ NOT ] **LIKE** *Pattern*  [ ESCAPE  *EscapeChar*  ] 
  
**LIKE** 运算符包含下列参数 
  
|**参数名称**|**必需**|**描述**|
|:-----|:-----|:-----|
| *Expression*  <br/> |是  <br/> |一个有效的表达式。  <br/> |
| *Pattern*  <br/> |是  <br/> |表达式 中要搜索的特定字符  *字符串*  。 可以包含通配符。 有关有效通配符的列表，请参阅"说明"。  <br/> |
| *EscapeChar*  <br/> |否  <br/> |放在通配符前面的字符，用于指示通配符应解释为常规字符而不是通配符。  *EscapeChar*  是一个没有默认值的字符表达式，其计算结果只能为一个字符。  <br/> |
   
## <a name="remarks"></a>备注

下表包含有效用于 Pattern 参数的  *通配符*  。 
  
|**通配符**|**说明**|**示例**|
|:-----|:-----|:-----|
|%  <br/> |零个或多个字符的任何字符串。  <br/> | *WHERE title LIKE '%computer%'*  finds all book titles with the word 'computer' anywhere in the book title.  <br/> |
|_（下划线字符）  <br/> |任意单个字符。  <br/> | *WHERE au_fname LIKE '_ean'*  finds all four-letter first names that end with ean (，Sean， and so on) .  <br/> |
|[]  <br/> |指定范围内的任何单个字符 ([a-f]) 或 ([abcdef]) 。  <br/> | *WHERE au_lname LIKE '[C-P]arsen'*  finds author last names ending with arsen and starting with any single character between C and P， for example Carsen， Larsen， Karsen， and so on.  <br/> |
|[^]  <br/> |指定范围内的任何单个字符 ([^a-f]) 或 ([^abcdef]) 。  <br/> | *WHERE au_lname LIKE 'de[^l]%'*  all author last names starting with de and where the following letter is not l.  <br/> |
   
使用 LIKE 执行字符串比较 **时，** 模式字符串中所有字符都重要。 这包括前导或尾随空格。 如果查询中的比较是返回字符串 **LIKE** 'abc ' (abc 后跟单个空格) 的所有行，则不返回该列的值为 abc (abc) 。 但是，模式匹配的表达式中的尾随空白将被忽略。 如果查询中的比较是返回字符串 **LIKE** 'abc' (abc 的所有行，而不返回空格) ，则返回以 abc 开头且尾部有零个或多个空白的所有行。 
  
如果任一参数不是字符串数据类型，它将转换为字符串数据类型，如果可能。
  

