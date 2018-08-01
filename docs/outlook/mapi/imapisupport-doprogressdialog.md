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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 527a7bb3201a4a6b1bc0807136bc88b80c189de2
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775621"
---
# <a name="imapisupportdoprogressdialog"></a>IMAPISupport::DoProgressDialog

  
  
**适用于**： Outlook 
  
检索一个进度对象，它显示进度指示器。
  
```cpp
HRESULT DoProgressDialog(
  ULONG_PTR ulUIParam,
  ULONG ulFlags,
  LPMAPIPROGRESS FAR * lppProgress
);
```

## <a name="parameters"></a>参数

 _ulUIParam_
  
> [in]进度指示器的父窗口句柄。
    
 _ulFlags_
  
> [in]位掩码的标志的控件的进度对象应如何计算进度。 可以设置以下标记：
    
MAPI_TOP_LEVEL 
  
> 顶级项目，如父文件夹计算进度。 进度对象应[IMAPIProgress::Progress](imapiprogress-progress.md)方法的_ulCount_和_ulTotal_参数中使用的值，其中分别指示当前项目和操作中的项 — 递增进度此操作的指示器。 
    
 _lppProgress_
  
> [输出]指向进度对象的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功检索进度对象。
    
## <a name="remarks"></a>说明

对于通讯簿和消息存储提供程序支持对象实现**IMAPISupport::DoProgressDialog**方法。 这些提供程序调用**DoProgressDialog**来访问 MAPI 实现的[IMAPIProgress](imapiprogressiunknown.md)接口，计算进度信息并显示一个标准的对话框。 
  
有关如何使用进度对象和**IMAPIProgress**接口的信息，请参阅[显示进度指示器](how-to-display-a-progress-indicator.md)。
  
## <a name="see-also"></a>另请参阅



[IMAPIProgress : IUnknown](imapiprogressiunknown.md)
  
[IMAPIProgress::Progress](imapiprogress-progress.md)
  
[IMAPISupport : IUnknown](imapisupportiunknown.md)


[显示进度指示器](how-to-display-a-progress-indicator.md)

