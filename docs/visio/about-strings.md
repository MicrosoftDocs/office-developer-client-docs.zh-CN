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
description: '公式中可包含字符串。 要设置字符串输出的格式（例如在提示单元格中的一个形状数据项的值，或者一个文本域），您可以指定一种格式图片。 可以设置输出的格式为数字单位对、字符串、日期时间、持续时间或货币。 例如，格式 picture0 #/10 uuformat 将数字单位对 10.9cm 作为 10 9/10 厘米。'
ms.openlocfilehash: aa95e11db387913edbb40292f7da6a0f4b8a5cf7
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33409515"
---
# <a name="about-strings"></a>关于字符串

公式中可包含字符串。要设置字符串输出的格式（例如在提示单元格中的一个形状数据项的值，或者一个文本域），您可以指定一种格式图片。可以设置输出的格式为数字单位对、字符串、日期时间、持续时间或货币。例如，格式图片 "0 #/10 uu" 将数字单位对 10.9cm 设置为 "10 9/10 厘米" 格式。
  
可以在"形状数据"节的 **Format** 单元格中将格式图片用作 **FORMAT** 或 **FORMATEX** 函数的参数。 插入文本域后，格式图片会显示在 **“域”** 对话框（**“插入”** 选项卡）的格式列表中。 
  
## <a name="using-functions-to-format-strings"></a>使用函数设置字符串格式

在解析为字符串的任何公式（包括自定义文本域公式）中，可以使用 **FORMAT** 或 **FORMATEX** 函数。 FORMAT 函数将返回已设定格式的输出字符串。 **FORMATEX** 函数将未键入的输入转换为为格式化结果选择的单位。 
  
## <a name="displaying-formatted-shape-data"></a>显示已设定格式的形状数据

您可以通过在 Format 单元格中输入格式图片来设置形状数据项的显示值的格式。
  
例如，项目时间线形状可以具有估算流程成本的形状数据项。默认情况下，形状数据项的值是字符串。要设置字符串 "1200" 的格式，可以在 Format 单元格中输入 "$###,###.00"，使用户看到货币值。
  
Microsoft Visio控制面板中"区域"和"语言"项中"自定义格式"对话框中"货币"选项卡上的设置来确定要显示的货币符号和千位分隔符。   (**控制面板中**，单击"区域 **"和"语言**"，然后单击"其他设置 **.)**
  
要将字符串转换为货币值以便用它执行计算，请使用 CY 函数。
  
## <a name="using-functions-to-manipulate-text-strings"></a>使用函数操作文本字符串

可以使用函数来操作文本字符串，例如，找到或替换文本字符串中的特定字符。还可以获取关于字符串中字符位置的信息，或标识文本字符串的开始和结束字符。 
  

