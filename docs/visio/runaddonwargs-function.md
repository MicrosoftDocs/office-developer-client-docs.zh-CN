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
description: 运行字符串并将命令行参数作为字符串传递给程序。
ms.openlocfilehash: bc05a4480438875c348373059f57bf04f82c9eca
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33408703"
---
# <a name="runaddonwargs-function"></a>RUNADDONWARGS 函数

运行_字符串_并将命令行_参数_作为字符串传递给程序。 
  
## <a name="syntax"></a>语法

RUNADDONWARGS ("* * *string* * *", "* * *arguments* * *") 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _string_ <br/> |必需  <br/> |**String** <br/> | 加载项的名称。  <br/> |
| _自_ <br/> |必需  <br/> |**String** <br/> |要传递给程序的参数。  <br/> |
   
## <a name="remarks"></a>说明

在实践中,_参数_应为50个字符或更少。 使用 RUNADDONWARGS 函数将一个程序（如加载项）绑定到一个单元格（例如，Action 单元格或 Events 单元格）上。 
  
RUNADDONWARGS 函数只能运行属于应用程序的 **Addons** 集合的成员的加载项。 要加入该集合的加载项必须是 EXE 文件或 VSL 文件，且： 
  
- 安装在应用程序的 **“Startup”** 或 **“Addons”** 路径中。 
    
- 使用 **Addons** 集合的 **Add** 方法，以编程方式添加。 
    
有关在 Visio 中运行代码的详细信息，请参阅本“ShapeSheet 参考”中的[关于 Visio 中的安全设置和运行代码](about-security-settings-and-running-code-in-visio-shapesheet.md)。 
  
在 Visio 的早期版本中，此函数以 _RUNADDONWARGS 的形式出现。Visio 应用程序 4.0 版和更高版本接受这两种样式中的任意一种。
  
## <a name="example"></a>示例

RUNADDONWARGS ("GRAPHMKR"。EXE ","/GraphMaker = Stack ") 
  
启动加载项 Graphmkr.exe 并向它传递参数 /GraphMaker=Stack。 
  

