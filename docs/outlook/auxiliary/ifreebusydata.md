---
title: IFreeBusyData
manager: soliver
ms.date: 12/08/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: c9a80ad3-6311-fe07-b6f7-9fd63424753b
ms.openlocfilehash: cd9d4dffd83e1995319b0f0d661435fedb78f28c
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32317496"
---
# <a name="ifreebusydata"></a>IFreeBusyData

对于给定用户, 获取并设置时间范围, 并返回一个用于枚举此时间范围内的忙/闲数据块的接口。
  
## <a name="quick-info"></a>快速信息

|||
|:-----|:-----|
|继承自:  <br/> |[IUnknown](https://msdn.microsoft.com/library/33f1d79a-33fc-4ce5-a372-e08bda378332%28Office.15%29.aspx) <br/> |
|提供者：  <br/> |闲/忙提供商  <br/> |
|接口标识符:  <br/> |IID_IFreeBusyData  <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序

|||
|:-----|:-----|
|[Placeholder1](ifreebusydata-placeholder1.md) <br/> | *此成员是占位符, 不受支持。*  <br/> |
|[EnumBlocks](ifreebusydata-enumblocks.md) <br/> |获取一个接口, 用于在指定的时间范围内枚举用户的忙/闲数据块。  <br/> |
|[Placeholder2](ifreebusydata-placeholder2.md) <br/> | *此成员是占位符, 不受支持。*  <br/> |
|[Placeholder3](ifreebusydata-placeholder3.md) <br/> | *此成员是占位符, 不受支持。*  <br/> |
|[Placeholder4](ifreebusydata-placeholder4.md) <br/> | *此成员是占位符, 不受支持。*  <br/> |
|[Placeholder5](ifreebusydata-placeholder5.md) <br/> | *此成员是占位符, 不受支持。*  <br/> |
|[SetFBRange](ifreebusydata-setfbrange.md) <br/> |设置用户的忙/闲数据块枚举的时间范围。  <br/> |
|[Placeholder6](ifreebusydata-placeholder6.md) <br/> | *此成员是占位符, 不受支持。*  <br/> |
|[GetFBPublishRange](ifreebusydata-getfbpublishrange.md) <br/> |获取用户的忙/闲数据块枚举的预设时间范围。  <br/> |
   
## <a name="remarks"></a>注解

此接口中的大多数成员是为 Outlook 内部使用而保留的占位符, 可能会发生更改。 闲/忙提供程序必须仅在指定的情况下实现这些提供程序, 才只返回指定的返回值。
  
## <a name="see-also"></a>另请参阅

- [关于忙/闲 API](about-the-free-busy-api.md)
- [常量 (忙/闲 API)](constants-free-busy-api.md)

