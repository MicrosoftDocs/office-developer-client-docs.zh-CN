---
title: ITnef IUnknown
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- ITnef
api_type:
- COM
ms.assetid: eddca896-9497-4425-9904-87ef3cbae298
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 1f815a914deb5e21f3d913abe46a84cc7a32b4ee
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33428513"
---
# <a name="itnef--iunknown"></a>ITnef : IUnknown

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
提供用于将邮件系统不支持的 MAPI 属性封装到可附加到邮件的二进制流的方法。 用于此封装的格式是 TNEF Transport-Neutral封装 (格式) 。 然后，目标传输提供程序或基于 MAPI 的客户端应用程序可以在接收包含 TNEF 附件的邮件时，从附件恢复属性。
  
|||
|:-----|:-----|
|标头文件：  <br/> |Tnef.h  <br/> |
|公开者：  <br/> |TNEF 对象  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |传输提供程序、邮件存储提供程序和网关  <br/> |
|接口标识符：  <br/> |IID_ITNEF  <br/> |
|指针类型：  <br/> |LPTNEF  <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序

|||
|:-----|:-----|
|[AddProps](itnef-addprops.md) <br/> |允许呼叫服务提供商或网关将属性添加到邮件或附件的封装中。  <br/> |
|[ExtractProps](itnef-extractprops.md) <br/> |从 TNEF 封装中提取属性。  <br/> |
|[Finish](itnef-finish.md) <br/> |完成排队和等待的所有 TNEF 操作的处理。  <br/> |
|[OpenTaggedBody](itnef-opentaggedbody.md) <br/> |打开封装邮件的文本上的流接口。  <br/> |
|[SetProps](itnef-setprops.md) <br/> |在不修改原始邮件或附件的情况下设置封装邮件或附件的一个或多个属性的值。  <br/> |
|[EncodeRecips](itnef-encoderecips.md) <br/> |对邮件的 TNEF 数据流中邮件收件人表的视图进行编码。  <br/> |
|[FinishComponent](itnef-finishcomponent.md) <br/> |将邮件中的单个组件一次处理一个处理到 TNEF 流中。  <br/> |
   
## <a name="see-also"></a>另请参阅



[MAPI 接口](mapi-interfaces.md)

