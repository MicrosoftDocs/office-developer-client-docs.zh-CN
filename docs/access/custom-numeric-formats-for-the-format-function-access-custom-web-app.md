---
title: Format 函数的自定义数值格式（Access 自定义 Web 应用）
manager: kelbow
ms.date: 08/18/2017
ms.audience: Developer
ms.assetid: 97efe972-d873-47d7-be81-8ae3461870c4
description: 了解如何通过创建用户定义的数字格式控制数字的显示方式。
localization_priority: Priority
ms.openlocfilehash: b23b1f7ee806a03df8f1c0d6ec1de0f3282b427b
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32282199"
---
# <a name="custom-numeric-formats-for-the-format-function-access-custom-web-app"></a>Format 函数的自定义数值格式（Access 自定义 Web 应用）

了解如何通过创建用户定义的数字格式控制数字的显示方式。
  
> [!IMPORTANT]
> Microsoft 不再建议在 SharePoint 中创建和使用 Access Web 应用程序。作为备选方法，请考虑使用 [Microsoft PowerApps](https://powerapps.microsoft.com/zh-CN/)，生成适用于 Web 和移动设备的无代码业务解决方案。 

可以通过创建用户定义的数字格式来更改数字的显示方式。 用户定义的数字格式可具有 1 到 3 个分区，以分号 (;) 分隔。 如果 [Format 函数（Access 自定义 Web 应用）](format-function-access-custom-web-app.md)的“样式”参数包含预定义的数值格式之一，则只允许有 1 个分区。 
  
## <a name="format-specifications"></a>Format 规范
<a name="bk_addresources"> </a>

下表列出了可用于创建用户定义的数字格式的字符。
  
|**Format 规范**|**说明**|
|:-----|:-----|
|无  <br/> |显示的数字没有任何格式。  <br/> |
|**0**（0 字符）  <br/> |数字占位符。 显示一个数字或 0。 如果表达式在格式字符串中的显示 0 的位置有一个数字，则显示该数字；否则，将在该位置显示 0。  <br/> 如果数字在格式表达式中具有的位数少于零的数目（小数点的两边），则显示前导零或尾随零。 如果数字在格式表达式中的小数分隔符右边具有的位数多于小数分隔符右边的零的数目，则将对该数字进行四舍五入（小数位的数目与零的数目相等）。 如果数字在格式表达式中的小数分隔符左边具有的位数多于小数分隔符左边的零的数目，则显示多余的位数而无需进行修改。  <br/> |
|#  <br/> |数字占位符。 显示一个数字或不显示任何内容。 如果表达式在格式字符串中的显示 0 的位置有一个数字，则显示该数字；否则，将在该位置不显示任何内容。  <br/> 此符号的工作方式与 0 数字占位符完全类似，只不过当数字在格式表达式中具有的数位少于小数分隔符两边的 # 字符的数目时，不显示前导零或尾随零。  <br/> |
|. （句点字符）  <br/> |小数点占位符。 小数点占位符决定小数分隔符左边和右边显示的数位。 如果格式表达式只在此符号左边包括 # 字符，则小于 1 的数字将以小数分隔符开头。 若要显示随小数一起显示的前导零，请将 0 用作小数分隔符左边的第一个数字占位符。 在部分区域，将逗号用作小数分隔符。 在格式化的输出中用作小数占位符的实际字符取决于系统所识别的数字格式。 因此，即便所在区域将逗号用作小数分隔符，也应使用句点作为小数占位符。 格式化的字符串将以适合于所在区域的正确格式显示。  <br/> |
|%  <br/> |百分比占位符。 表达式乘以 100。 百分号 (%) 将插入其在格式字符串中出现的位置。  <br/> |
|,（逗号分隔符）  <br/> |千位分隔符。 千位分隔符将在小数分隔符左边具有四个或更多位的数字中分隔千位和百位。 如果格式包含由数字占位符（0 或 # ）包围的千位分隔符，则将指定千位分隔符的标准用法。  <br/> 紧靠小数分隔符左边或字符串最右边位置的字符的千位分隔符（无论是否已指定小数）表示“将数字除以 1,000 进行缩放，按需舍入”。 小于 1,000 但大于或等于 500 的数字显示为 1，小于 500 的数字显示为 0。 此位置中的两个相邻千位分隔符按比例因子 1 百万进行缩放，其他分隔符按比例因子 1,000 缩放。  <br/> 在紧靠小数分隔符左边的位置之外的任何其他位置或字符串最右边位置的多个分隔符将被简单对待，就像指定千位分隔符的用法一样。 在部分区域，句点用作千位分隔符。 在格式化的输出中用作千位分隔符的实际字符取决于系统所识别的数字格式。 因此，即便所在区域将句点用作千位分隔符，也应使用逗号作为千位分隔符。 格式化的字符串将以适合于所在区域的正确格式显示。  <br/> 例如，请考虑以下三种格式字符串：  <br/> “#,0.”，该字符串使用千位分隔符将数字 1 亿表示为字符串“100,000,000”。  <br/> “#0,.”，该字符串使用比例因子 1,000 将数字 1 亿表示为字符串“100000”。  <br/> “#,0,.”，该字符串使用千位分隔符和比例因子 1,000 将数字 1 亿显示为字符串“100,000”。  <br/> |
|:（冒号字符）  <br/> |时间分隔符。 在一些区域设置中，可使用其他字符表示时间分隔符。 在设置时间值格式时，时间分隔符用于分隔小时、分钟和秒。 在格式化输出中用作时间分隔符的实际字符由系统设置决定。  <br/> |
|/（正斜杠字符）  <br/> |日期分隔符。 在部分区域，也可以使用其他字符表示日期分隔符。 在设置日期值格式时，日期分隔符用于分隔天、月和年。 在格式化输出中用作日期分隔符的实际字符由系统设置决定。  <br/> |
|**E-、E+、e-、e+** <br/> |科学记数法格式。 如果格式表达式在 E-、E+、e- 或 e+ 的左边至少包括一个数字占位符（0 或 # ），则数字以科学记数法格式显示，并且 E 或 e 将插入该数字与其指数之间。 左边的数字占位符的数目将决定指数中的位数。 使用 E- 或 e- 可在负指数旁边放置减号。 使用 E+ 或 e+ 可以在负指数旁边放置减号并在正指数旁边放置加号。 此外，必须在此符号的右边包含数字占位符才能获得正确的格式。  <br/> |
|**- + $ ( )** <br/> |文本字符。 这些字符按格式字符串中键入的内容显示。 若要显示所列字符之外的字符，请在该字符前面加反斜杠 (\) 或将其用双引号括起来 (" ")。  <br/> |
|\ （反斜杠字符）  <br/> |显示格式字符串中的下一个字符。 若要将具有特殊意义的字符显示为文本字符，请在该字符前面加反斜杠 (\)。 反斜杠本身不会显示。 使用反斜杠与使用双引号将下一个字符括起来的效果相同。 若要显示反斜杠，请使用双反斜杠 (\\)。  <br/> 无法显示为文本字符的字符示例包括日期格式和时间格式字符（a、c、d、h、m、n、p、q、s、t、w、y、/ 和 :）、数字格式字符（#、0、%、E、e、逗号和句点）以及字符串格式字符（@、&amp;、\<、\> 和 !）。  <br/> |
|"ABC"  <br/> |显示双引号 (" ") 中的字符。 若要包含代码内的样式参数中的字符串，必须使用 Chr(34) 将文本括起来（34 为引号 (") 的字符代码）。  <br/> |
   
下表包含一些数字的示例格式表达式。 （这些示例全部假定系统区域设置为 English-U.S.）。第一列包含 Format 函数的格式字符串。 当格式化数据中包含列标题中给定的值时，其他列包含结果输出。
  
|**Format（样式）**|**“5”格式化为**|**“-5”格式化为**|**“0.5”格式化为**|**“0”格式化为**|
|:-----|:-----|:-----|:-----|:-----|
|零长度字符串 ("")  <br/> |5  <br/> |-5  <br/> |0.5  <br/> |0  <br/> |
|0  <br/> |5  <br/> |-5  <br/> |1  <br/> |0  <br/> |
|0.00  <br/> |5.00  <br/> |-5.00  <br/> |0.50  <br/> |0.00  <br/> |
|#,##0  <br/> |5  <br/> |-5  <br/> |1  <br/> |0  <br/> |
|$#,##0;($#,##0)  <br/> |$5  <br/> |($5)  <br/> |$1  <br/> |$0  <br/> |
|$#,##0.00;($#,##0.00)  <br/> |$5.00  <br/> |($5.00)  <br/> |$0.50  <br/> |$0.00  <br/> |
|0%  <br/> |500%  <br/> |-500%  <br/> |50%  <br/> |0%  <br/> |
|0.00%  <br/> |500.00%  <br/> |-500.00%  <br/> |50.00%  <br/> |0.00%  <br/> |
|0.00E+00  <br/> |5.00E+00  <br/> |-5.00E+00  <br/> |5.00E-01  <br/> |0.00E+00  <br/> |
|0.00E-00  <br/> |5.00E00  <br/> |-5.00E00  <br/> |5.00E-01  <br/> |0.00E00  <br/> |
|"$#,##0;;\Z\e\r\o"  <br/> |$5  <br/> |$-5  <br/> |$1  <br/> |0  <br/> |
   
## <a name="remarks"></a>备注
<a name="bk_addresources"> </a>

如果包含多个分号，而这些分号之间没有任何内容，则将使用正值的格式显示缺少的部分。
  
## <a name="see-also"></a>另请参阅

- [Format 函数（Access 自定义 Web 应用）](format-function-access-custom-web-app.md) 
- [Format 函数的自定义日期和时间格式（Access 自定义 Web 应用）](custom-date-and-time-formats-for-the-format-function-access-custom-web-app.md)
  

