---
title: PLAYSOUND 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm82251479
localization_priority: Normal
ms.assetid: 098d216f-e699-0e74-f702-ccfa7809c19b
description: 播放声音文件或系统声音。
ms.openlocfilehash: 752412aab6584d2b01235fe88644e3ec3fa5daee
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33435836"
---
# <a name="playsound-function"></a>PLAYSOUND 函数

播放声音文件或系统声音。 
  
## <a name="syntax"></a>语法

PLAYSOUND ("* * *filename* * *" | "* * *alias* * *", * * *isAlias* * *, * **提示音** *, * * *synch* * *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _filename_ <br/> |必需  <br/> |**String** <br/> |要播放的声音文件的名称。  <br/> |
| _alias_ <br/> |必需  <br/> |**String** <br/> | 由别名表示的系统声音。  <br/> |
| _isAlias_ <br/> |必需  <br/> |**Boolean** <br/> | 指定前面的表达式是别名还是文件名；使用非零值来指定别名。  <br/> |
| _发声_ <br/> |必需  <br/> |**Boolean** <br/> |指定在声音无法播放时，Microsoft Visio 是否发出嘟嘟声；使用非零数字来指定发出嘟嘟声。  <br/> |
| _同步_ <br/> |必需  <br/> |**Boolean** <br/> |确定是异步 (0) 播放声音还是同步 (1) 播放声音。  <br/> |
   
## <a name="remarks"></a>说明

通常应异步播放声音，这样 Visio 就能够在播放声音的同时继续进行处理。 若要将几种声音组合在一起，请同步播放它们，否则一些声音可能无法播放。 
  
## <a name="example-1"></a>示例 1

PLAYSOUND("chord.wav", 0, 0, 0)
  
无警告嘟嘟声，异步播放音频文件 chord.wav。
  
## <a name="example-2"></a>示例 2

PLAYSOUND("SystemExclamation", 1, 0, 0)
  
无警告嘟嘟声，异步播放系统感叹声。
  

