---
title: RUNADDONWARGS 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251493
localization_priority: Normal
ms.assetid: c154413f-c366-a66b-94e3-ed71ad23f325
description: 运行字符串，并将命令行参数传递给字符串形式的程序。
ms.openlocfilehash: 7bc05a0cbf32550d1e39bee39bec83101882cf19
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781208"
---
# <a name="runaddonwargs-function"></a>RUNADDONWARGS 函数

运行_字符串_，并将命令行_参数_传递给字符串形式的程序。 
  
## <a name="syntax"></a>语法

RUNADDONWARGS ("* **字符串** *"、"* **参数** *") 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _string_ <br/> |必需  <br/> |**字符串** <br/> | 加载项的名称。  <br/> |
| _参数_ <br/> |必需  <br/> |**字符串** <br/> |要传递给程序的参数。  <br/> |
   
## <a name="remarks"></a>注解

实际上，_参数_应为 50 个或更少字符。 使用 RUNADDONWARGS 函数将程序，如加载项，对单元格，例如，绑定到操作或事件单元格。 
  
RUNADDONWARGS 函数只能运行加载项的应用程序的**Addons**集合的成员。 必须包含在集合中，加载项必须是 EXE 文件或 VSL 文件： 
  
- 安装应用程序的**启动**或**Addons**路径中。 
    
- 使用**Addons**集合的**Add**方法以编程方式添加。 
    
有关在 Visio 中运行代码的详细信息，请参阅[关于安全设置和运行 Visio 中的代码](about-security-settings-and-running-code-in-visio-shapesheet.md)在 ShapeSheet 参考。 
  
在 Visio 的早期版本中，此函数以 _RUNADDONWARGS 的形式出现。Visio 应用程序 4.0 版和更高版本接受这两种样式中的任意一种。
  
## <a name="example"></a>示例

RUNADDONWARGS ("GRAPHMKR。Exe 文件"，"/ GraphMaker = 堆栈") 
  
启动加载项 Graphmkr.exe 并向它传递参数 /GraphMaker=Stack。 
  

