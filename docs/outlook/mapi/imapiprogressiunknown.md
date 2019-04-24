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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32270075"
---
# <a name="imapiprogress--iunknown"></a>IMAPIProgress : IUnknown

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
实现为客户端应用程序提供进度指示器的进度对象。 进度指示器是显示操作完成百分比的用户界面显示, 如在邮件存储之间复制文件夹。 MAPI 和客户端应用程序实施进度对象, 服务提供程序使用它们。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |mapidefs。h  <br/> |
|公开者:  <br/> |进度对象  <br/> |
|实现者：  <br/> |MAPI 和客户端应用程序  <br/> |
|调用者：  <br/> |服务提供程序  <br/> |
|接口标识符:  <br/> |IID_IMAPIProgress  <br/> |
|指针类型:  <br/> |LPMAPIPROGRESS  <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序

|||
|:-----|:-----|
|[Progress](imapiprogress-progress.md) <br/> |将进度指示器更新为在完成操作时显示进度。  <br/> |
|[GetFlags](imapiprogress-getflags.md) <br/> |返回用于计算进度信息的操作级别的进度对象中的标志设置。  <br/> |
|[GetMax](imapiprogress-getmax.md) <br/> |返回显示其进度信息的操作中的最大项目数。  <br/> |
|[GetMin](imapiprogress-getmin.md) <br/> |返回显示其进度信息的[SetLimits](imapiprogress-setlimits.md)方法中的最小值。  <br/> |
|[SetLimits](imapiprogress-setlimits.md) <br/> |为操作中的项目数以及控制如何为操作计算进度信息的标志设置上限和下限。  <br/> |
   
## <a name="remarks"></a>注解

MAPI 在许多方法中都包含_lpProgress_参数, 这些方法执行可能的漫长操作。  _lpProgress_指向进度对象的客户端实现。 实现**IMAPIProgress**接口的客户端将此参数设置为指向其实现;未实现**IMAPIProgress**的客户端将参数设置为 NULL。 若要在操作的过程中显示进度指示器, 服务提供程序使用客户端提供的进度对象 (如果有) 或 MAPI 实现 (当_lpProgress_设置为 NULL 时指示)。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**Files**|**函数**|**备注**|
|:-----|:-----|:-----|
|MapiProgress 和 MapiProgress  <br/> |不适用  <br/> |如果启用了 IMAPIProgress 设置, MFCMAPI 将向 MFCMAPI 调用的接受实现的所有函数传递**IMAPIProgress**实现。  <br/> |
   
## <a name="see-also"></a>另请参阅



[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)
  
[MAPI 接口](mapi-interfaces.md)

