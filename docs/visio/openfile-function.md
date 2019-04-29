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
description: 如果 Microsoft Visio 文档尚未打开, 则将其打开, 并激活文档窗口。
ms.openlocfilehash: 5a89a658e560d144007ec19796de82b9949bea82
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33419574"
---
# <a name="openfile-function"></a>OPENFILE 函数

如果 Microsoft Visio 文档尚未打开, 则将其打开, 并激活文档窗口。
  
## <a name="syntax"></a>语法

 **OPENFILE**( _"filename"_)
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _filename_ <br/> |必需  <br/> |**String** <br/> |要打开的文件的名称, 包括文件路径。  <br/> |
   
## <a name="remarks"></a>说明

多个 OPENFILE 函数调用将按照计算次序排队执行。如果当前的 Visio 文档正处于可视（就地）编辑状态，则用请求的文件名启动新的 Visio 实例。 
  
此函数总是返回 FALSE。 
  
在 Visio 应用程序的早期版本中，此函数以 _OPENFILE 的形式出现。Visio 4.0 版和更高版本接受这两种样式中的任意一种。 
  
## <a name="example"></a>示例

 `OPENFILE("C:/MyFile.vsdx")`
  
在新窗口中打开指定的文件 "MyFile", 如果该文件已打开, 则激活该窗口。 
  

