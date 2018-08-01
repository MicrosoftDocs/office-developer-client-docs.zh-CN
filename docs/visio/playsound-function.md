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
ms.openlocfilehash: ca54b749b764e9ea2c7db71d41268303542417f0
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19780899"
---
# <a name="playsound-function"></a>PLAYSOUND 函数

播放声音文件或系统声音。 
  
## <a name="syntax"></a>语法

PLAYSOUND ("* * *filename* * *"|"* **别名** *"，* * *isAlias* * *，* **嘟嘟声** *，* **同步** *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _文件名_ <br/> |必需  <br/> |**字符串** <br/> |要播放的声音文件的名称。  <br/> |
| _alias_ <br/> |必需  <br/> |**字符串** <br/> | 由别名表示的系统声音。  <br/> |
| _isAlias_ <br/> |必需  <br/> |**Boolean** <br/> | 指定前面的表达式是别名还是文件名；使用非零值来指定别名。  <br/> |
| _beep_ <br/> |必需  <br/> |**Boolean** <br/> |指定在声音无法播放时，Microsoft Visio 是否发出嘟嘟声；使用非零数字来指定发出嘟嘟声。  <br/> |
| _同步_ <br/> |必需  <br/> |**Boolean** <br/> |确定是异步 (0) 播放声音还是同步 (1) 播放声音。  <br/> |
   
## <a name="remarks"></a>注解

通常应异步播放声音，这样 Visio 就能够在播放声音的同时继续进行处理。若要将几种声音组合在一起，请同步播放它们，否则一些声音可能无法播放。
 
  
## <a name="example-1"></a>示例 1

PLAYSOUND("chord.wav", 0, 0, 0)
  
无警告嘟嘟声，异步播放音频文件 chord.wav。
  
## <a name="example-2"></a>示例 2

PLAYSOUND("SystemExclamation", 1, 0, 0)
  
无警告嘟嘟声，异步播放系统感叹声。
  

