---
title: IFreeBusyData
manager: soliver
ms.date: 12/08/2015
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: c9a80ad3-6311-fe07-b6f7-9fd63424753b
ms.openlocfilehash: cd9d4dffd83e1995319b0f0d661435fedb78f28c
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25393206"
---
# <a name="ifreebusydata"></a>IFreeBusyData

为给定的用户、 获取和设置一个时间范围并返回枚举忙/闲此时间范围内的数据块界面。
  
## <a name="quick-info"></a>快速信息

|||
|:-----|:-----|
|继承：  <br/> |[IUnknown](https://msdn.microsoft.com/library/33f1d79a-33fc-4ce5-a372-e08bda378332%28Office.15%29.aspx) <br/> |
|提供者：  <br/> |忙/闲提供程序  <br/> |
|接口标识符：  <br/> |IID_IFreeBusyData  <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序排列

|||
|:-----|:-----|
|[Placeholder1](ifreebusydata-placeholder1.md) <br/> | *此成员是一个占位符，不支持。*  <br/> |
|[EnumBlocks](ifreebusydata-enumblocks.md) <br/> |获取枚举忙/闲数据块的指定的时间范围内的用户界面。  <br/> |
|[Placeholder2](ifreebusydata-placeholder2.md) <br/> | *此成员是一个占位符，不支持。*  <br/> |
|[Placeholder3](ifreebusydata-placeholder3.md) <br/> | *此成员是一个占位符，不支持。*  <br/> |
|[Placeholder4](ifreebusydata-placeholder4.md) <br/> | *此成员是一个占位符，不支持。*  <br/> |
|[Placeholder5](ifreebusydata-placeholder5.md) <br/> | *此成员是一个占位符，不支持。*  <br/> |
|[SetFBRange](ifreebusydata-setfbrange.md) <br/> |设置用户的忙/闲数据块枚举的时间范围。  <br/> |
|[Placeholder6](ifreebusydata-placeholder6.md) <br/> | *此成员是一个占位符，不支持。*  <br/> |
|[GetFBPublishRange](ifreebusydata-getfbpublishrange.md) <br/> |获取一个预设的时间范围的忙/闲信息的用户数据块枚举。  <br/> |
   
## <a name="remarks"></a>说明

大部分此接口中的成员保留供内部使用的 Outlook 的占位符，并受到更改。 忙/闲提供程序必须实现它们仅作为指定，返回仅指定的返回值。
  
## <a name="see-also"></a>另请参阅

- [关于忙/闲 API](about-the-free-busy-api.md)
- [常量 (忙/闲 API)](constants-free-busy-api.md)

