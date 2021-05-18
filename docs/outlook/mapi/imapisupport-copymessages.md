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
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33405154"
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
  
> [in]指向接口标识符 (IID) 表示用于访问包含要复制或移动的邮件的文件夹的接口的指针。
    
 _lpSrcFolder_
  
> [in]指向包含要复制或移动的邮件的文件夹的指针。
    
 _lpMsgList_
  
> [in]指向标识要复制或移动的消息的条目标识符数组的指针。 
    
 _lpDestInterface_
  
> [in]指向接口标识符的指针 (IID) 表示用于访问复制或移动的邮件的目标文件夹的接口。
    
 _lpDestFolder_
  
> [in]指向复制或移动的邮件的目标文件夹的指针。 此文件夹必须打开。
    
 _ulUIParam_
  
> [in]指向显示进度指示器的进度对象的指针。 如果在  _lpProgress_ 中传递 NULL，则邮件存储提供程序使用 MAPI 进度对象实现显示进度指示器。 除非在 _ulFlags_ 中设置了 MESSAGE_DIALOG 标志，否则将忽略 _lpProgress_ 参数。
    
 _lpProgress_
  
> [in]指向显示进度指示器的进度对象的指针。 如果在  _lpProgress_ 中传递 NULL，则邮件存储提供程序使用 MAPI 进度对象实现显示进度指示器。 除非在 _ulFlags_ 中设置了 MESSAGE_DIALOG 标志，否则将忽略 _lpProgress_ 参数。
    
 _ulFlags_
  
> [in]控制复制或移动操作完成方式的标志的位掩码。 可以设置以下标志：
    
MESSAGE_DIALOG 
  
> 请求进度指示器的显示。
    
MESSAGE_MOVE 
  
> 应移动而不是复制邮件。 如果未MESSAGE_MOVE，则复制邮件。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 复制或移动操作成功。
    
MAPI_E_USER_CANCEL 
  
> 用户通常通过单击对话框中的"取消" **按钮来取消** 操作。 
    
## <a name="remarks"></a>备注

**IMAPISupport：：CopyMessages** 方法为邮件存储提供程序支持对象实现。 邮件存储提供程序可以在 **IMAPIFolder：：CopyMessages 的实现中调用 IMAPISupport：：CopyMessages，** 以将一个或多个邮件从一个文件夹复制或移动到另一个文件夹。 [](imapifolder-copymessages.md) 作为 **IMAPISupport：：CopyMessages** 调用的一部分，邮件存储提供程序可以指定 MAPI 应显示进度指示器。 
  
## <a name="see-also"></a>另请参阅



[IMAPIFolder::CopyMessages](imapifolder-copymessages.md)
  
[IMAPISupport : IUnknown](imapisupportiunknown.md)

