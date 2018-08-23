---
title: 初始化 MAPI 的 OLE
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 53b65299-69f8-4fc0-8d9b-f666e814aaac
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: cd279c17574ce73b42d5e07e96ac817af71dc700
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22589803"
---
# <a name="initializing-ole-for-mapi"></a>初始化 MAPI 的 OLE

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
如果您还使用 OLE，调用 OLE 函数[OleInitialize](http://msdn.microsoft.com/en-us/library/ms690134%28v=VS.85%29.aspx)初始化 OLE 库。 **OleInitialize**会话初始化全局数据，并准备 OLE 库以接受呼叫。 调用**OleInitialize**有关的信息，请参阅 Windows SDK。
  

