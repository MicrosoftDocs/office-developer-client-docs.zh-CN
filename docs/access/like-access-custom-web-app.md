---
title: LIKE (Access 自定义 web 应用)
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: decdd8fc-2184-4d97-b918-3ef6ab1ab40b
description: 确定特定字符串是否与指定的模式相匹配。 模式可以包含常规字符和通配符字符。 在模式匹配期间, 常规字符必须与字符字符串中指定的字符完全匹配。 但是, 通配符可以与字符串的任意段相匹配。 与使用 = 和! = 字符串比较运算符相比, 使用通配符可使 LIKE 运算符更灵活。
ms.openlocfilehash: 02d1e4f8fc61335e828a1f77579c14b1c7577485
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32311079"
---
# <a name="like-access-custom-web-app"></a>LIKE (Access 自定义 web 应用)

确定特定字符串是否与指定的模式相匹配。 模式可以包含常规字符和通配符字符。 在模式匹配期间, 常规字符必须与字符字符串中指定的字符完全匹配。 但是, 通配符可以与字符串的任意段相匹配。 与使用 = 和! = 字符串比较运算符相比, 使用通配符可使**LIKE**运算符更灵活。 
  
> [!IMPORTANT]
> Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。 
  
## <a name="syntax"></a>语法

 *表达式* 不要**LIKE***模式* [ESCAPE *EscapeChar* ] 
  
**LIKE**运算符包含以下参数 
  
|**参数名称**|**必需**|**描述**|
|:-----|:-----|:-----|
| *Expression*  <br/> |是  <br/> |一个有效的表达式。  <br/> |
| *Pattern*  <br/> |是  <br/> |要在*表达式*中搜索的特定字符串的字符。 可以包含通配符字符。 请参阅备注获取有效通配符字符的列表。  <br/> |
| *EscapeChar*  <br/> |否  <br/> |放在通配符前面的字符, 用于指示通配符应被解释为常规字符, 而不是通配符。  *EscapeChar*是一个不含默认值的字符表达式, 并且必须仅取值为一个字符。  <br/> |
   
## <a name="remarks"></a>注解

下表包含可在*Pattern*参数中使用的有效通配符字符。 
  
|**通配符**|**说明**|**示例**|
|:-----|:-----|:-----|
|%  <br/> |任何零个或多个字符的字符串。  <br/> | *其中标题 (如 "% computer%"* ) 查找书名中带有 "computer" 一词的所有书籍标题。  <br/> |
|_（下划线字符）  <br/> |任意单个字符。  <br/> | *其中, au_fname (如 "_ean"* ) 查找以 ean (Dean、小红等) 结尾的所有四个字母的名字。  <br/> |
|[]  <br/> |指定范围内的任意单个字符 ([a-f]) 或 set ([abcdef])。  <br/> | *其中 au_lname LIKE "[C-P] arsen"* 查找作者姓以 arsen 开头, 并以 C 和 P 之间的任何单个字符开始, 例如 Carsen、Larsen、Karsen 等等。  <br/> |
|[^]  <br/> |不在指定范围 ([^ a-f]) 或 set ([^ abcdef]) 内的任何单个字符。  <br/> | *其中, au_lname (如 "de [^ l]%")* 所有作者姓以 de 开头, 并且在以下字母不是 l。  <br/> |
   
使用**LIKE**执行字符串比较时, 模式字符串中的所有字符都非常重要。 这包括前导空格或尾随空格。 如果查询中的比较结果是返回一个字符串 (abc 后跟**** 一个空格) 的所有行, 则不返回该列的值为 abc (abc 不带空格) 的行。 但是, 将忽略模式与之匹配的表达式中的尾随空白。 如果查询中的比较结果是返回字符串中包含 "abc" **** (abc 不带空格) 的所有行, 则返回以 "abc" 开头且具有零个或多个尾随空格的所有行。 
  
如果任何一个参数不是 string 数据类型, 则会将其转换为 string 数据类型 (如果可能)。
  

