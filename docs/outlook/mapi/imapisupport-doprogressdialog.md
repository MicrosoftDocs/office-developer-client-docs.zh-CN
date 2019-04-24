---
title: IMAPISupportDoProgressDialog
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISupport.DoProgressDialog
api_type:
- COM
ms.assetid: 74c52b96-e903-444b-8bda-73a08f278c22
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 3de29e9af5caa82d2e57c8fcbbdab7d5ddb19dd9
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32285204"
---
# <a name="imapisupportdoprogressdialog"></a>IMAPISupport::DoProgressDialog

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
检索显示进度指示器的进度对象。
  
```cpp
HRESULT DoProgressDialog(
  ULONG_PTR ulUIParam,
  ULONG ulFlags,
  LPMAPIPROGRESS FAR * lppProgress
);
```

## <a name="parameters"></a>参数

 _ulUIParam_
  
> 实时进度指示器的父窗口的句柄。
    
 _ulFlags_
  
> 实时标志的位掩码, 用于控制进度对象应如何计算进度。 可以设置以下标志:
    
MAPI_TOP_LEVEL 
  
> 对顶级项目 (如父文件夹) 的进度进行计算。 进度对象应使用[IMAPIProgress::P rogress](imapiprogress-progress.md)方法的_ulCount_和_ulTotal_参数中的值, 它们分别指示当前项和操作中的项目总数, 以增加进度操作的指示器。 
    
 _lppProgress_
  
> 排除指向进度对象的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功检索进度对象。
    
## <a name="remarks"></a>注解

**IMAPISupport::D oprogressdialog**方法是为通讯簿和邮件存储提供程序支持对象实现的。 这些提供程序调用**DoProgressDialog**以访问[IMAPIProgress](imapiprogressiunknown.md)接口的 MAPI 实现, 这将计算进度信息并显示标准对话框。 
  
有关如何使用进度对象和**IMAPIProgress**接口的信息, 请参阅[显示进度指示器](how-to-display-a-progress-indicator.md)。
  
## <a name="see-also"></a>另请参阅



[IMAPIProgress : IUnknown](imapiprogressiunknown.md)
  
[IMAPIProgress::Progress](imapiprogress-progress.md)
  
[IMAPISupport : IUnknown](imapisupportiunknown.md)


[显示进度指示器](how-to-display-a-progress-indicator.md)

