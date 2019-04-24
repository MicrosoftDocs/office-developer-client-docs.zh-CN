---
title: IEnumFBBlock
manager: soliver
ms.date: 12/08/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: fad9c0fd-b523-db98-ee0d-78aad5914ff2
ms.openlocfilehash: 2b37aa2000218acc0663ee8e2db12f01b93c0663
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32317624"
---
# <a name="ienumfbblock"></a>IEnumFBBlock

支持在某个时间范围内访问和枚举用户的忙/闲数据块。
  
## <a name="quick-info"></a>快速信息

|||
|:-----|:-----|
|继承自:  <br/> |[IUnknown](https://msdn.microsoft.com/library/33f1d79a-33fc-4ce5-a372-e08bda378332%28Office.15%29.aspx) <br/> |
|提供者：  <br/> |闲/忙提供商  <br/> |
|接口标识符:  <br/> |**IEnumFBBlock** <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序

|||
|:-----|:-----|
|[Next](ienumfbblock-next.md) <br/> |获取枚举中的下一个指定数量的忙/闲数据块。  <br/> |
|[Skip](ienumfbblock-skip.md) <br/> |跳过指定数量的忙/闲数据块。  <br/> |
|[Reset](ienumfbblock-reset.md) <br/> |通过将游标设置为开头来重置枚举数。  <br/> |
|[Clone](ienumfbblock-clone.md) <br/> |使用相同的时间限制创建枚举数的副本, 但将游标设置为枚举器的开头。  <br/> |
|[Restrict](ienumfbblock-restrict.md) <br/> |将枚举限制在指定时间段内。  <br/> |
   
## <a name="remarks"></a>注解

枚举包含不能按时重叠的忙/闲数据块。 当日历上有重叠项目时, Outlook 将基于此优先级顺序, 合并这些项目以形成枚举中不重叠的忙/闲块: 外出、忙碌、暂定。
  
忙/闲提供程序通过[IFreeBusyData](ifreebusydata.md)获取用户的时间范围的此接口和枚举。
  
## <a name="see-also"></a>另请参阅

- [关于忙/闲 API](about-the-free-busy-api.md)  
- [常量 (忙/闲 API)](constants-free-busy-api.md)  
- [IFreeBusyData](ifreebusydata.md)

