---
title: 像 （访问自定义 web 应用程序）
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: decdd8fc-2184-4d97-b918-3ef6ab1ab40b
description: 确定特定字符串是否与指定的模式匹配。 模式可以包含常规字符和通配符。 模式匹配时，常规字符必须完全匹配字符串中指定的字符。 但是，通配符可以与字符串的任意部分相匹配。 使用通配符可使 LIKE 运算符比使用 = 更灵活和 ！ = 字符串比较运算符。
ms.openlocfilehash: d3224647c621b05a08bdc863939d0cccae214463
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773487"
---
# <a name="like-access-custom-web-app"></a>像 （访问自定义 web 应用程序）

确定特定字符串是否与指定的模式匹配。 模式可以包含常规字符和通配符。 模式匹配时，常规字符必须完全匹配字符串中指定的字符。 但是，通配符可以与字符串的任意部分相匹配。 使用通配符可使**LIKE**运算符比使用 = 更灵活和 ！ = 字符串比较运算符。 
  
> [!IMPORTANT]
> Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/en-us/)，生成适用于 Web 和移动设备的无代码业务解决方案。 
  
## <a name="syntax"></a>语法

 *表达式* [NOT]**像***模式* [转义*EscapeChar* ] 
  
**LIKE**运算符包含以下参数 
  
|**参数名称**|**必需**|**说明**|
|:-----|:-----|:-----|
| *Expression*  <br/> |可访问  <br/> |一个有效表达式。  <br/> |
| *Pattern*  <br/> |可访问  <br/> |要在*表达式*中搜索特定字符串。 可以包含通配符字符。 引用一组有效通配符字符的备注。  <br/> |
| *EscapeChar*  <br/> |否  <br/> |应解释通配符放置通配符来指示前面的字符，为常规字符，而不是通配符。  *EscapeChar*是没有默认值和计算结果必须为只有一个字符的字符表达式。  <br/> |
   
## <a name="remarks"></a>说明

下表包含有效的*模式*参数中使用通配符。 
  
|**通配符**|**说明**|**示例**|
|:-----|:-----|:-----|
|%  <br/> |零个或多个字符的任意字符串。  <br/> | *其中 title '%计算机 %' 像*查找的单词计算机的所有书名任意位置中书籍标题。  <br/> |
|_（下划线字符）  <br/> |任意单个字符。  <br/> | *像 _ean WHERE au_fname*查找 ean （Dean、 Sean，等等） 结尾的所有四个字母第一个名称。  <br/> |
|[]  <br/> |任何单个字符指定区域 ([a-f]) 中或设置 (例如 [abcdef])。  <br/> | *位置 au_lname 类似 [C-P] arsen*查找创作姓氏结尾 arsen 和启动之间有任意单个字符 C 和 P，例如 Carsen，Larsen，Karsen，等等。  <br/> |
|[^]  <br/> |任何单个字符不在指定范围内的 ([^ 为 a-f]) 或设置 ([^ abcdef])。  <br/> | *如位置 au_lname de [^ l] %'* 所有作者开头 de 和以下号不 l 的最后一个姓名。  <br/> |
   
时使用**如**执行字符串比较，模式字符串中的所有字符都都有意义。 这包括前导或尾随空格。 如果要在查询中的比较返回所有行，**如**字符串 abc (abc 跟一个空格)，则不返回的行顺序的列的值是 abc (abc 后没有空格)。 但是，向其匹配模式，该表达式中的尾随空格将被忽略。 如果在查询中的比较是所有一起返回行**类似**的字符串 abc (不带空格的 abc)，则返回所有行的开头 abc 和具有零个或多个尾随空格。 
  
如果任一参数不是字符串数据类型，它转换为 string 数据类型，如果可能。
  

