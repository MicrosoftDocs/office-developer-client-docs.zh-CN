---
title: 为 MAPI 初始化 OLE
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 53b65299-69f8-4fc0-8d9b-f666e814aaac
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 87310916f4a54b308f0599ec5c1a4a3bfe83c376
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32317225"
---
# <a name="initializing-ole-for-mapi"></a>为 MAPI 初始化 OLE

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
如果还使用 ole, 请调用 ole 函数[OleInitialize](https://msdn.microsoft.com/library/ms690134%28v=VS.85%29.aspx)以初始化 ole 库。 **OleInitialize**为会话初始化全局数据, 并准备 OLE 库以接受调用。 有关调用**OleInitialize**的信息, 请参阅 Windows SDK。
  

