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
ms.openlocfilehash: 1803707b46b9b58e7372e7e58cc36241d0ebdb4d
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22571722"
---
# <a name="itnef--iunknown"></a>ITnef : IUnknown

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
提供用于封装到可附加到邮件的二进制流不支持的邮件系统的 MAPI 属性的方法。 用于此封装的格式是传输中性封装格式 (TNEF)。 目标传输提供程序或基于 MAPI 的客户端应用程序可以然后，在收到一条消息，包括 TNEF 附件时恢复属性附件。
  
|||
|:-----|:-----|
|头文件：  <br/> |Tnef.h  <br/> |
|由公开：  <br/> |TNEF 对象  <br/> |
|通过实现：  <br/> |MAPI  <br/> |
|调用：  <br/> |传输提供程序、 消息存储提供程序，和网关  <br/> |
|接口标识符：  <br/> |IID_ITNEF  <br/> |
|指针类型：  <br/> |LPTNEF  <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序排列

|||
|:-----|:-----|
|[AddProps](itnef-addprops.md) <br/> |允许将属性添加到邮件或附件封装调用服务提供商或网关。  <br/> |
|[ExtractProps](itnef-extractprops.md) <br/> |从 TNEF 封装提取属性。  <br/> |
|[Finish](itnef-finish.md) <br/> |处理排队的所有 TNEF 操作和等待完成。  <br/> |
|[OpenTaggedBody](itnef-opentaggedbody.md) <br/> |打开上封装的消息的文本的流接口。  <br/> |
|[SetProps](itnef-setprops.md) <br/> |设置用于封装的邮件或附件的一个或多个属性的值，而无需修改原始邮件或附件。  <br/> |
|[EncodeRecips](itnef-encoderecips.md) <br/> |将编码 TNEF 数据流的邮件中的消息的收件人表视图。  <br/> |
|[FinishComponent](itnef-finishcomponent.md) <br/> |到 TNEF stream 一次处理从一个一条消息的各个组件。  <br/> |
   
## <a name="see-also"></a>另请参阅



[MAPI 接口](mapi-interfaces.md)

