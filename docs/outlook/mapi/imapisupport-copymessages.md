---
title: IMAPISupportCopyMessages
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISupport.CopyMessages
api_type:
- COM
ms.assetid: 70f67614-af0d-43f6-99f6-391a2f5673cb
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 9cc4e3ba77395e09a6b95e8381fa402fc3cdff61
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32356530"
---
# <a name="imapisupportcopymessages"></a>IMAPISupport::CopyMessages

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
将邮件从一个文件夹复制或移动到另一个文件夹。
  
```cpp
HRESULT CopyMessages(
  LPCIID lpSrcInterface,
  LPVOID lpSrcFolder,
  LPENTRYLIST lpMsgList,
  LPCIID lpDestInterface,
  LPVOID lpDestFolder,
  ULONG_PTR ulUIParam,
  LPMAPIPROGRESS lpProgress,
  ULONG ulFlags
);
```

## <a name="parameters"></a>参数

 _lpSrcInterface_
  
> 实时指向接口标识符 (IID) 的指针, 该接口标识符表示用于访问包含要复制或移动的邮件的文件夹的接口。
    
 _lpSrcFolder_
  
> 实时指向包含要复制或移动的邮件的文件夹的指针。
    
 _lpMsgList_
  
> 实时指向条目标识符数组的指针, 这些标识符标识要复制或移动的邮件。 
    
 _lpDestInterface_
  
> 实时指向接口标识符 (IID) 的指针, 该接口标识符代表要用于访问已复制或移动的邮件的目标文件夹的接口。
    
 _lpDestFolder_
  
> 实时指向已复制或移动邮件的目标文件夹的指针。 此文件夹必须处于打开状态。
    
 _ulUIParam_
  
> 实时指向显示进度指示器的进度对象的指针。 如果在_lpProgress_中传递 NULL, 则邮件存储提供程序将使用 MAPI 进度对象实现来显示进度指示器。 除非在_ulFlags_中设置了 MESSAGE_DIALOG 标志, 否则_lpProgress_参数将被忽略。
    
 _lpProgress_
  
> 实时指向显示进度指示器的进度对象的指针。 如果在_lpProgress_中传递 NULL, 则邮件存储提供程序将使用 MAPI 进度对象实现来显示进度指示器。 除非在_ulFlags_中设置了 MESSAGE_DIALOG 标志, 否则_lpProgress_参数将被忽略。
    
 _ulFlags_
  
> 实时用于控制如何完成复制或移动操作的标志的位掩码。 可以设置以下标志:
    
MESSAGE_DIALOG 
  
> 请求显示进度指示器。
    
MESSAGE_MOVE 
  
> 应移动邮件, 而不是复制。 如果未设置 MESSAGE_MOVE, 则会复制邮件。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 复制或移动操作成功完成。
    
MAPI_E_USER_CANCEL 
  
> 用户取消了操作, 通常是单击对话框中的 "**取消**" 按钮。 
    
## <a name="remarks"></a>注解

为邮件存储提供程序支持对象实现了**IMAPISupport:: CopyMessages**方法。 邮件存储提供程序可以在其[IMAPIFolder:: CopyMessages](imapifolder-copymessages.md)的实现中调用**IMAPISupport:: CopyMessages** , 将一个或多个邮件从一个文件夹复制或移动到另一个文件夹。 作为**IMAPISupport:: CopyMessages**调用的一部分, 邮件存储提供程序可以指定 MAPI 应显示进度指示器。 
  
## <a name="see-also"></a>另请参阅



[IMAPIFolder::CopyMessages](imapifolder-copymessages.md)
  
[IMAPISupport : IUnknown](imapisupportiunknown.md)

