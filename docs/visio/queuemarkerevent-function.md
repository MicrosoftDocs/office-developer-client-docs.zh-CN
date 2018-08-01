---
title: QUEUEMARKEREVENT 函数
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
f1_keywords:
- Vis_DSS.chm60107
localization_priority: Normal
ms.assetid: b4671715-4209-7774-c174-c19dc9721a02
description: 将导致触发到您的加载项，Microsoft Visual Basic for Applications (VBA) 代码或 COM 加载项的标记事件的应用程序。
ms.openlocfilehash: b9175caf0845530c93f6db15e286f3eae21ea415
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19781003"
---
# <a name="queuemarkerevent-function"></a>QUEUEMARKEREVENT 函数

将导致触发到您的加载项，Microsoft Visual Basic for Applications (VBA) 代码或 COM 加载项的标记事件的应用程序。 
  
## <a name="syntax"></a>语法

QUEUEMARKEREVENT (* * *event_string* * *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _event_string_ <br/> |必需  <br/> |**字符串** <br/> | 要传递给事件处理程序的字符串。  <br/> |
   
## <a name="remarks"></a>说明

QUEUEMARKEREVENT 函数为开发人员提供一种方法来通知从 ShapeSheet 单元格，其代码并将特定于解决方案的信息传递。 包含与 QUEUEMARKEREVENT 函数的公式的单元格计算时，应用程序实例将触发标记事件，并将_event_string_传递给**MarkerEvent**事件侦听的所有事件处理程序。 
  
有关标记事件的详细信息，请参阅**QueueMarkerEvent**方法和**MarkerEvent**事件主题 Microsoft Visio 自动化参考中。 
  
## <a name="example"></a>示例

QUEUEMARKEREVENT ("MyCustomNotification") 
  
导致应用程序触发标记事件，并将字符串“MyCustomNotification”传递给正在侦听 **MarkerEvent** 事件的事件处理程序。 
  

