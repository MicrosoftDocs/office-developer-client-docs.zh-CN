---
title: OPENFILE 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251471
localization_priority: Normal
ms.assetid: ff59ab04-a589-cf9e-db3b-20658a7dffdc
description: 如果其尚未打开，并激活文档窗口，请打开 Microsoft Visio 文档。
ms.openlocfilehash: 7d4778fc4641465e88303b8515365172fd8be0ff
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780811"
---
# <a name="openfile-function"></a>OPENFILE 函数

如果其尚未打开，并激活文档窗口，请打开 Microsoft Visio 文档。
  
## <a name="syntax"></a>语法

 **OPENFILE**( _"文件名"_)
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _文件名_ <br/> |必需  <br/> |**字符串** <br/> |要打开该文件，包括文件路径的名称。  <br/> |
   
## <a name="remarks"></a>注解

多个 OPENFILE 函数调用将按照计算次序排队执行。如果当前的 Visio 文档正处于可视（就地）编辑状态，则用请求的文件名启动新的 Visio 实例。 
  
此函数总是返回 FALSE。 
  
在 Visio 应用程序的早期版本中，此函数以 _OPENFILE 的形式出现。Visio 4.0 版和更高版本接受这两种样式中的任意一种。 
  
## <a name="example"></a>示例

 `OPENFILE("C:/MyFile.vsdx")`
  
在新窗口中，打开指定的文件"MyFile.vsdx"，或如果文件已打开，则激活窗口。 
  

