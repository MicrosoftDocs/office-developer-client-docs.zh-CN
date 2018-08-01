---
title: 与 IStreamDocfile 打开 OLE 附件
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: f91df63c-ff6d-4c63-a665-5bcfdabe7e0e
description: 上次修改时间： 2012 年 7 月 6 日
ms.openlocfilehash: 33e5b9e0112f562b192400498764a10682d006a6
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776571"
---
# <a name="opening-ole-attachments-with-istreamdocfile"></a>与 IStreamDocfile 打开 OLE 附件

**适用于**： Outlook 
  
在打开附件 OLE 对象时，使用**IStreamDocfile**接口而不是[IStream](http://msdn.microsoft.com/en-us/library/windows/desktop/aa380034%28v=vs.85%29.aspx)或[IStorage](http://msdn.microsoft.com/en-us/library/windows/desktop/aa380015%28v=vs.85%29.aspx)。 

**IStreamDocfile**提供直接访问使用结构化的存储文件，不需要执行复制操作和减少开销的对象。 **IStreamDocfile** **IStream**保证格式化为结构化存储 stream 的内容具体的实现。 由消息存储提供程序实现**IStreamDocfile** 。 
  

