---
title: OLE 附件
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: febb6a5e-7c40-4f21-806e-7f827d1c37cf
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: fb716ce014ec3c4b21ce2b021c1a9f6f291d511c
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33417145"
---
# <a name="ole-attachments"></a>OLE 附件

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
作为向后兼容性, ole 对象的附件被编码为 ole 1 stream 对象。 如果原始对象实际上是 OLE 2 **IStorage**对象, 则必须将该对象转换为 ole 1 流。 此转换是使用**OleConvertIStorageToOLESTREAM**函数 (Win32 OLE 库的一部分) 执行的。 
  

