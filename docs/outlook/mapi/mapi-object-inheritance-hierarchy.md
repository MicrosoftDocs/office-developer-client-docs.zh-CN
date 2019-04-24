---
title: MAPI 对象继承层次结构
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 3dc0b79f-e346-416d-ac81-42eba6b6d3b2
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 4b610415089ff19165ffcabc9e13901ed63c907d
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32345836"
---
# <a name="mapi-object-inheritance-hierarchy"></a>MAPI 对象继承层次结构

**适用于**：Outlook 2013 | Outlook 2016 
  
MAPI 对象实现的所有接口最终继承自[IUnknown](https://msdn.microsoft.com/library/33f1d79a-33fc-4ce5-a372-e08bda378332%28Office.15%29.aspx), 这是允许对象进行通信的 OLE 接口。 大多数接口直接继承自**IUnknown**, 但某些接口继承自以下两个基接口之一: [IMAPIProp: IUnknown](imapipropiunknown.md)或[IMAPIContainer: IMAPIProp](imapicontainerimapiprop.md)。 下图显示了 MAPI 中的完整继承层次结构。
  
**MAPI 继承层次结构**
  
![MAPI 继承层次结构](media/amapi_06.gif "MAPI 继承层次结构")
  
## <a name="see-also"></a>另请参阅

- [IMAPIProp : IUnknown](imapipropiunknown.md) 
- [IMAPIContainer : IMAPIProp](imapicontainerimapiprop.md)
- [MAPI 对象和接口概述](mapi-object-and-interface-overview.md)

