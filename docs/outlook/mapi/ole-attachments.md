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
ms.openlocfilehash: ccd4a77e74a4a4cbdfcd8474d4cc00d0d0516839
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22584637"
---
# <a name="ole-attachments"></a>OLE 附件

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
附件的 OLE 对象被编码为向后兼容性的 OLE 1 stream 对象。 如果原始对象确实是 OLE 2 **IStorage**对象，该对象必须要转换到 OLE 1 流。 使用**OleConvertIStorageToOLESTREAM**函数，它是 Win32 OLE 库的一部分，则执行此转换。 
  

