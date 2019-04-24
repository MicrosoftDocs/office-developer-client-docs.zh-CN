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
description: 使应用程序触发对加载项的标记事件、Microsoft Visual Basic for Applications (VBA) 代码或 COM 加载项。
ms.openlocfilehash: 841f6acc63497a6f0b8930c89534b5f8b04c0393
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32358723"
---
# <a name="queuemarkerevent-function"></a>QUEUEMARKEREVENT 函数

使应用程序触发对加载项的标记事件、Microsoft Visual Basic for Applications (VBA) 代码或 COM 加载项。 
  
## <a name="syntax"></a>语法

QUEUEMARKEREVENT (* * *event_string* * *) 
  
### <a name="parameters"></a>参数

|**名称**|**必需/可选**|**数据类型**|**说明**|
|:-----|:-----|:-----|:-----|
| _event_string_ <br/> |必需  <br/> |**String** <br/> | 要传递给事件处理程序的字符串。  <br/> |
   
## <a name="remarks"></a>注解

借助 QUEUEMARKEREVENT 函数，开发人员可以通知 ShapeSheet 单元格中的代码，然后传递特定于解决方案的信息。 计算包含包含 QUEUEMARKEREVENT 函数的公式的单元格时, 应用程序触发标记事件并将_event_string_传递给正在侦听**MarkerEvent**事件的所有事件处理程序。 
  
有关标记事件的详细信息, 请参阅 Microsoft Visio Automation Reference 中的**QueueMarkerEvent**方法和**MarkerEvent**事件主题。 
  
## <a name="example"></a>示例

QUEUEMARKEREVENT ("MyCustomNotification") 
  
导致应用程序触发标记事件，并将字符串“MyCustomNotification”传递给正在侦听 **MarkerEvent** 事件的事件处理程序。 
  

