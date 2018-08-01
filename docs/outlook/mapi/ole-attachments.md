---
title: OLE 附件
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: febb6a5e-7c40-4f21-806e-7f827d1c37cf
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: b95b83ad7eedff577e4c36365c9e451f4b458173
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776537"
---
# <a name="ole-attachments"></a>OLE 附件

  
  
**适用于**： Outlook 
  
附件的 OLE 对象被编码为向后兼容性的 OLE 1 stream 对象。 如果原始对象确实是 OLE 2 **IStorage**对象，该对象必须要转换到 OLE 1 流。 使用**OleConvertIStorageToOLESTREAM**函数，它是 Win32 OLE 库的一部分，则执行此转换。 
  

