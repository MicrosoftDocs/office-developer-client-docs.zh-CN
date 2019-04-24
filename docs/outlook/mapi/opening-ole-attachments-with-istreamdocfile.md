---
title: 使用 IStreamDocfile 打开 OLE 附件
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: f91df63c-ff6d-4c63-a665-5bcfdabe7e0e
description: '上次修改时间: 2006 年7月2012'
ms.openlocfilehash: 2de13be34e8d81f88bfba872dda6e5534eb431bd
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32326227"
---
# <a name="opening-ole-attachments-with-istreamdocfile"></a>使用 IStreamDocfile 打开 OLE 附件

**适用于**：Outlook 2013 | Outlook 2016 
  
打开 OLE 对象附件时, 请使用**IStreamDocfile**接口, 而不是[IStream](https://msdn.microsoft.com/library/windows/desktop/aa380034%28v=vs.85%29.aspx)或[IStorage](https://msdn.microsoft.com/library/windows/desktop/aa380015%28v=vs.85%29.aspx)。 

**IStreamDocfile**提供了使用结构化存储的直接访问对象, 消除了执行复制操作和减少开销的需求。 **IStreamDocfile**是一个特定的**IStream**实现, 可保证流的内容被格式化为结构化存储。 **IStreamDocfile**是由邮件存储提供程序实现的。 
  

