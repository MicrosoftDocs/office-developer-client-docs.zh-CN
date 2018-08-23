---
title: MAPI 对象继承层次结构
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 3dc0b79f-e346-416d-ac81-42eba6b6d3b2
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 4b2b9971677312dbea297c9fe2d29ba65174904d
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22588788"
---
# <a name="mapi-object-inheritance-hierarchy"></a>MAPI 对象继承层次结构

**适用于**： Outlook 2013 |Outlook 2016 
  
实现 MAPI 对象的所有接口最终都继承[IUnknown](http://msdn.microsoft.com/library/33f1d79a-33fc-4ce5-a372-e08bda378332%28Office.15%29.aspx)，使对象进行通信的 OLE 接口。 大多数界面直接继承**IUnknown**，但某些从其他两个基本接口之一继承： [IMAPIProp: IUnknown](imapipropiunknown.md)或[IMAPIContainer: IMAPIProp](imapicontainerimapiprop.md)。 下图显示 MAPI 中的完整继承层次结构。
  
**MAPI 继承层次结构**
  
![MAPI 继承层次结构](media/amapi_06.gif "MAPI 继承层次结构")
  
## <a name="see-also"></a>另请参阅

- [IMAPIProp : IUnknown](imapipropiunknown.md) 
- [IMAPIContainer : IMAPIProp](imapicontainerimapiprop.md)
- [MAPI 对象和接口概述](mapi-object-and-interface-overview.md)

