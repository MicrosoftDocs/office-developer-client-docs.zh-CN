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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 64b2c147acb02b6c29cf080076b6fe2e3eefb717
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775592"
---
# <a name="imapisupportcopymessages"></a>IMAPISupport::CopyMessages

  
  
**适用于**： Outlook 
  
复制或移动邮件从一个文件夹到另一个文件夹。
  
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
  
> [in]指向接口标识 (IID) 值，该值代表要用于访问该文件夹包含的邮件复制或移动的接口的指针。
    
 _lpSrcFolder_
  
> [in]一个指向包含邮件复制或移动的文件夹。
    
 _lpMsgList_
  
> [in]一个指向的标识的邮件复制或移动的项标识符数组。 
    
 _lpDestInterface_
  
> [in]指向接口标识 (IID) 值，该值代表要用于访问的复制或移动邮件的目标文件夹的接口的指针。
    
 _lpDestFolder_
  
> [in]一个指向的复制或移动邮件的目标文件夹。 此文件夹必须打开。
    
 _ulUIParam_
  
> [in]指向显示进度指示器进度对象的指针。 如果在_lpProgress_传递 NULL，则消息存储提供程序将使用 MAPI 进度对象实现显示进度指示器。 除非_ulFlags_中设置了 MESSAGE_DIALOG 标志，则将忽略该_lpProgress_参数。
    
 _lpProgress_
  
> [in]指向显示进度指示器进度对象的指针。 如果在_lpProgress_传递 NULL，则消息存储提供程序将使用 MAPI 进度对象实现显示进度指示器。 除非_ulFlags_中设置了 MESSAGE_DIALOG 标志，则将忽略该_lpProgress_参数。
    
 _ulFlags_
  
> [in]位掩码的标志，控制如何完成复制或移动操作。 可以设置以下标志：
    
MESSAGE_DIALOG 
  
> 请求进度指示器的显示。
    
MESSAGE_MOVE 
  
> 应移动邮件，而不是复制。 如果未设置 MESSAGE_MOVE，邮件所复制。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 复制或移动操作已成功。
    
MAPI_E_USER_CANCEL 
  
> 用户取消操作，通常通过单击对话框中的**取消**按钮。 
    
## <a name="remarks"></a>备注

消息存储提供程序支持对象的实现**IMAPISupport::CopyMessages**方法。 消息存储提供程序可以[IMAPIFolder::CopyMessages](imapifolder-copymessages.md)复制或移动到另一个文件夹中一个或多个邮件其实现中调用**IMAPISupport::CopyMessages** 。 作为**IMAPISupport::CopyMessages**呼叫的一部分，消息存储提供程序可以指定 MAPI 应显示进度指示器。 
  
## <a name="see-also"></a>另请参阅



[IMAPIFolder::CopyMessages](imapifolder-copymessages.md)
  
[IMAPISupport: IUnknown](imapisupportiunknown.md)

