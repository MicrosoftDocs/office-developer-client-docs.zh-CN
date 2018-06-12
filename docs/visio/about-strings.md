---
title: 关于字符串
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: overview
f1_keywords:
- Vis_DSS.chm82251826
localization_priority: Normal
ms.assetid: e1174d8f-70cb-4595-7906-889da15367db
description: '公式可包含字符串。 格式化字符串输出，如 prompt 单元格、 形状数据项的值或文本字段中，您指定的格式图片。 在设置输出格式为数字单位对、 字符串、 日期时间、 持续时间或货币。 例如，format picture0 #/ 10 uuformats 数字单位配对 10.9 厘米 as10 9/10 厘米。'
ms.openlocfilehash: 1fd003ecd5c824042e97a40fa8374aeead254ddc
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779604"
---
# <a name="about-strings"></a>关于字符串

公式中可包含字符串。要设置字符串输出的格式（例如在提示单元格中的一个形状数据项的值，或者一个文本域），您可以指定一种格式图片。可以设置输出的格式为数字单位对、字符串、日期时间、持续时间或货币。例如，格式图片 "0 #/10 uu" 将数字单位对 10.9cm 设置为 "10 9/10 厘米" 格式。
  
您可以在**Format**单元格的形状数据部分以及**格式**或**FORMATEX**函数的参数中使用格式图片。 插入的文本字段时，图片格式显示**字段**对话框 （在**插入**选项卡） 中的格式的列表中。 
  
## <a name="using-functions-to-format-strings"></a>使用函数设置字符串格式

在任何公式解析为字符串，包括自定义文本字段公式，您可以使用**格式**或**FORMATEX**函数。 FORMAT 函数返回字符串的格式化输出。 **FORMATEX**函数将转换类型的输入您为带格式的结果为单位的选择。 
  
## <a name="displaying-formatted-shape-data"></a>显示带格式的形状数据

您可以通过在 Format 单元格中输入格式图片来设置形状数据项的显示值的格式。
  
例如，项目时间线形状可以具有估算流程成本的形状数据项。默认情况下，形状数据项的值是字符串。要设置字符串 "1200" 的格式，可以在 Format 单元格中输入 "$###,###.00"，使用户看到货币值。
  
Microsoft Visio 使用控制面板中的**区域和语言**项中的**自定义格式**对话框中的**货币**选项卡上设置来确定的货币符号和千位分隔符显示。 （在**控制面板**中，单击**区域和语言选项**，然后单击**其他设置**。）
  
要将字符串转换为货币值以便用它执行计算，请使用 CY 函数。
  
## <a name="using-functions-to-manipulate-text-strings"></a>使用函数操作文本字符串

可以使用函数来操作文本字符串，例如，找到或替换文本字符串中的特定字符。还可以获取关于字符串中字符位置的信息，或标识文本字符串的开始和结束字符。 
  

