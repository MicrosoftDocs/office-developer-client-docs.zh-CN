---
title: IMAPIProgress IUnknown
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIProgress
api_type:
- COM
ms.assetid: 7a872296-0378-456f-b4d6-cb4d96b09d6e
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 3a3d54ac9485cc3915d3606bb84b4f3191d1ca5b
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33419644"
---
# <a name="imapiprogress--iunknown"></a>IMAPIProgress : IUnknown

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
实现一个进度对象，该对象为客户端应用程序提供进度指示器。 进度指示器是显示操作完成百分比的用户界面显示，例如复制邮件存储之间的文件夹。 MAPI 和客户端应用程序实现进度对象，服务提供商使用它们。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapidefs.h  <br/> |
|公开者：  <br/> |进度对象  <br/> |
|实现者：  <br/> |MAPI 和客户端应用程序  <br/> |
|调用者：  <br/> |服务提供程序  <br/> |
|接口标识符：  <br/> |IID_IMAPIProgress  <br/> |
|指针类型：  <br/> |LPMAPIPROGRESS  <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序

|||
|:-----|:-----|
|[Progress](imapiprogress-progress.md) <br/> |更新进度指示器，并显示在操作完成时的进度。  <br/> |
|[GetFlags](imapiprogress-getflags.md) <br/> |从计算进度信息的操作级别的进度对象中返回标志设置。  <br/> |
|[GetMax](imapiprogress-getmax.md) <br/> |返回操作中显示其进度信息的最大项目数。  <br/> |
|[GetMin](imapiprogress-getmin.md) <br/> |返回 [SetLimits](imapiprogress-setlimits.md) 方法中显示进度信息的最小值。  <br/> |
|[SetLimits](imapiprogress-setlimits.md) <br/> |设置操作中项数的下限和上限，以及控制如何计算操作进度信息的标志。  <br/> |
   
## <a name="remarks"></a>备注

MAPI 在很多执行可能过长操作的方法中包含  _lpProgress_ 参数。  _lpProgress_ 指向进度对象的客户端实现。 实现 **IMAPIProgress 接口** 的客户端设置此参数以指向其实现;不实现 **IMAPIProgress 的客户端将** 参数设置为 NULL。 若要在处理操作期间显示进度指示器，服务提供商将使用客户端提供的进度对象（如果可用）或 MAPI 实现 (当  _lpProgress_ 设置为 NULL) 。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**Files**|**函数**|**备注**|
|:-----|:-----|:-----|
|MapiProgress.h 和 MapiProgress.cpp  <br/> |不适用  <br/> |如果启用了 IMAPIProgress 设置，则 MFCMAPI 将 **IMAPIProgress** 实现传递给 MFCMAPI 调用接受实现的所有函数。  <br/> |
   
## <a name="see-also"></a>另请参阅



[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)
  
[MAPI 接口](mapi-interfaces.md)

