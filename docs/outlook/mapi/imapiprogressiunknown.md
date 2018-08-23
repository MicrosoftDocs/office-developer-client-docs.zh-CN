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
ms.openlocfilehash: 42d09fd92edf4dc221b73dac4948e78a7c6898ac
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22589327"
---
# <a name="imapiprogress--iunknown"></a>IMAPIProgress : IUnknown

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
实现提供与进度指示器的客户端应用程序的进度对象。 显示的操作，如复制文件夹消息存储库之间的完成百分比的用户界面显示进度指示器。 MAPI 和客户端应用程序实现进度对象，服务提供商使用它们。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapidefs.h  <br/> |
|由公开：  <br/> |进度对象  <br/> |
|通过实现：  <br/> |MAPI 和客户端应用程序  <br/> |
|调用：  <br/> |服务提供商  <br/> |
|接口标识符：  <br/> |IID_IMAPIProgress  <br/> |
|指针类型：  <br/> |LPMAPIPROGRESS  <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序排列

|||
|:-----|:-----|
|[Progress](imapiprogress-progress.md) <br/> |更新进度指示器进度的显示做出的操作完成。  <br/> |
|[GetFlags](imapiprogress-getflags.md) <br/> |返回标记的操作对其计算进度信息的级别的进度对象中的设置。  <br/> |
|[GetMax](imapiprogress-getmax.md) <br/> |对于的进度的信息将显示的操作中返回的最大项目数。  <br/> |
|[GetMin](imapiprogress-getmin.md) <br/> |对于的进度的信息将显示在[SetLimits](imapiprogress-setlimits.md)方法中返回的最小值。  <br/> |
|[SetLimits](imapiprogress-setlimits.md) <br/> |设置项的数目的上限和下限限制中操作，并且控制操作的进度信息的计算方式的标志。  <br/> |
   
## <a name="remarks"></a>注解

MAPI 中的许多方法执行可能长时间的操作包括_lpProgress_参数。  _lpProgress_指向进度对象的客户端实现。 客户端实现**IMAPIProgress**接口的设置此参数可指向其实现;客户端不实现**IMAPIProgress**参数设置为 NULL。 若要处理的操作过程中显示进度指示器，服务提供商使用的进度对象，提供由客户端，如果可用，或者 （指示_lpProgress_设置为 NULL 时） 的 MAPI 实现。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 参考 （英文）

MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**Comment**|
|:-----|:-----|:-----|
|MapiProgress.h 和 MapiProgress.cpp  <br/> |不适用  <br/> |如果启用 IMAPIProgress 设置后，MFCMAPI 将**IMAPIProgress**实现将传递给所有 MFCMAPI 调用接受实现的功能。  <br/> |
   
## <a name="see-also"></a>另请参阅



[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)
  
[MAPI 接口](mapi-interfaces.md)

