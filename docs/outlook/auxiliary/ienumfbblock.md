---
title: IEnumFBBlock
manager: soliver
ms.date: 12/08/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: fad9c0fd-b523-db98-ee0d-78aad5914ff2
ms.openlocfilehash: 2b37aa2000218acc0663ee8e2db12f01b93c0663
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25388187"
---
# <a name="ienumfbblock"></a>IEnumFBBlock

支持访问和枚举忙/闲时间范围内的用户数据块。
  
## <a name="quick-info"></a>快速信息

|||
|:-----|:-----|
|继承：  <br/> |[IUnknown](https://msdn.microsoft.com/library/33f1d79a-33fc-4ce5-a372-e08bda378332%28Office.15%29.aspx) <br/> |
|提供者：  <br/> |忙/闲提供程序  <br/> |
|接口标识符：  <br/> |**IEnumFBBlock** <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序排列

|||
|:-----|:-----|
|[下一步](ienumfbblock-next.md) <br/> |获取枚举中的下一个指定的数量的忙/闲数据块。  <br/> |
|[跳过](ienumfbblock-skip.md) <br/> |跳过指定的数量的忙/闲数据块。  <br/> |
|[Reset](ienumfbblock-reset.md) <br/> |通过将光标设置为开始重置枚举。  <br/> |
|[Clone](ienumfbblock-clone.md) <br/> |创建一份枚举数，使用相同的时间限制，但设置光标到枚举的开头。  <br/> |
|[限制](ienumfbblock-restrict.md) <br/> |限制到指定的时间段枚举。  <br/> |
   
## <a name="remarks"></a>说明

枚举包含忙/闲时间不重叠的数据块。 当日历上存在重叠的项目时，Outlook 将合并这些项目以形成枚举基于以下优先顺序中的非重叠忙/闲基块:-外出、 忙碌、 暂定。
  
忙/闲信息的提供程序获取该接口和时间范围内的用户通过[IFreeBusyData](ifreebusydata.md)枚举。
  
## <a name="see-also"></a>另请参阅

- [关于忙/闲 API](about-the-free-busy-api.md)  
- [常量 (忙/闲 API)](constants-free-busy-api.md)  
- [IFreeBusyData](ifreebusydata.md)

