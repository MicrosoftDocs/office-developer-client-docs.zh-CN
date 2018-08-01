---
title: IMAPIFolderCopyMessages
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIFolder.CopyMessages
api_type:
- COM
ms.assetid: 4c7d2110-3fcb-4b9f-bf20-1dc1a611161d
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: e6e9e9cefc75ffc78ee7beb47e89063ea1a66ce7
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19775345"
---
# <a name="imapifoldercopymessages"></a>IMAPIFolder::CopyMessages

  
  
**适用于**： Outlook 
  
复制或移动一个或多条消息。
  
```cpp
HRESULT CopyMessages(
  LPENTRYLIST lpMsgList,
  LPCIID lpInterface,
  LPVOID lpDestFolder,
  ULONG_PTR ulUIParam,
  LPMAPIPROGRESS lpProgress,
  ULONG ulFlags
);
```

## <a name="parameters"></a>参数

 _lpMsgList_
  
> [in]指向一个标识要复制或移动的消息的[ENTRYLIST](entrylist.md)结构数组的指针。 
    
 _lpInterface_
  
> [in]指向接口标识 (IID) 值，该值代表要用于访问_lpDestFolder_参数指向目标文件夹的接口的指针。 传递 NULL 将导致服务提供程序返回的标准文件夹接口， [IMAPIFolder: IMAPIContainer](imapifolderimapicontainer.md)。 客户端必须传递 NULL。 其他呼叫者可以设置为 IID_IUnknown、 IID_IMAPIProp、 IID_IMAPIContainer 或 IID_IMAPIFolder _lpInterface_参数。 
    
 _lpDestFolder_
  
> [in]指向打开接收复制或移动邮件文件夹的指针。
    
 _ulUIParam_
  
> [in]该方法显示的任何对话框或窗口的父窗口的句柄。 除非在客户端中_ulFlags_参数设置 MESSAGE_DIALOG 标志和_lpProgress_参数中传递 NULL，则将忽略该_ulUIParam_参数。 
    
 _lpProgress_
  
> [in]指向显示进度指示器进度对象的指针。 如果在_lpProgress_传递 NULL，则消息存储提供程序将使用 MAPI 进度对象实现显示进度指示器。 除非_ulFlags_中设置了 MESSAGE_DIALOG 标志，则将忽略该_lpProgress_参数。
    
 _ulFlags_
  
> [in]位掩码的标志，控制如何完成复制或移动操作。 可以设置以下标志：
    
MAPI_DECLINE_OK 
  
> 通知如果它通过调用支持对象的[IMAPISupport::DoCopyTo](imapisupport-docopyto.md)或[IMAPISupport::DoCopyProps](imapisupport-docopyprops.md)方法实现**IMAPIFolder::CopyMessages**立即返回 MAPI_E_DECLINE_COPY 消息存储提供程序。 
    
MESSAGE_DIALOG 
  
> 随着进行操作，则显示进度指示器。
    
MESSAGE_MOVE 
  
> 邮件或消息是移动而不是复制。 如果未设置 MESSAGE_MOVE，邮件所复制。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 邮件已成功复制或移动。
    
MAPI_E_DECLINE_COPY 
  
> 提供程序实现此方法通过调用支持对象方法，并且将呼叫者已传递 MAPI_DECLINE_OK 标志。
    
MAPI_W_PARTIAL_COMPLETION 
  
> 调用成功，但并非所有项已成功复制或移动。 返回此警告时，应处理呼叫为成功。 若要测试此警告，请使用**HR_FAILED**宏。 有关详细信息，请参阅[使用宏的错误处理](using-macros-for-error-handling.md)。
    
## <a name="remarks"></a>说明

**IMAPIFolder::CopyMessages**方法复制，或将邮件移动到另一个文件夹。 
  
使用打开的邮件读/写权限可以移动或复制。 
  
## <a name="notes-to-implementers"></a>针对实施者的注释

如果您到另一个消息存储库复制邮件，而无需使用[IMAPISupport::CopyMessages](imapisupport-copymessages.md)方法，您必须先调用[IMAPIFolder::SetReadFlags](imapifolder-setreadflags.md)设置了 GENERATE_RECEIPT_ONLY 标志。 接收方的消息存储不负责生成的复制或移动邮件阅读的报告。 如果您正在呼叫**IMAPISupport::CopyMessages**实现**IMAPIFolder::CopyMessages**，不会调用**SetReadFlags**;MAPI 将调用它。 
  
实现可以移动或复制的邮件，按任意顺序并按任意顺序生成读取的状态报告。 即可以完成之前生成读取的状态任何的报告复制邮件或实现开始复制操作之前发送报告。 但是，读取报告应发送的所有邮件不管副本是否成功复制。
  
当复制或移动操作涉及多个邮件时，请尽可能完整执行操作。 不停止操作提前除非超过了您的控件，如运行内存不足、 不足磁盘空间或损坏消息存储区中的出现故障。
  
尝试移动或复制操作在维护条目标识符。 尽管不需要，还应保留项标识符。
  
移动或复制邮件，以便客户端注意其调用邮件的[IMAPIProp::SaveChanges](imapiprop-savechanges.md)方法可能会失败时发送通知。 
  
不要在副本中包括邮件的状态或移动操作。 移动或复制邮件状态会显著影响性能。
  
## <a name="notes-to-callers"></a>给调用方的说明

使用**IMAPIFolder::CopyMessages**填充搜索结果文件夹，其中邮件通常组合的父文件夹。 
  
希望在下列情况下的这些返回值。
  
|**条件**|**返回值**|
|:-----|:-----|
|**IMAPIFolder::CopyMessages**已成功复制或移动的每条消息。  <br/> |S_OK  <br/> |
|**IMAPIFolder::CopyMessages**程序无法成功复制或移动的每条消息。  <br/> |MAPI_W_PARTIAL_COMPLETION  <br/> |
|**IMAPIFolder::CopyMessages**无法完成。  <br/> |任何错误值  <br/> |
   
无法完成**IMAPIFolder::CopyMessages**时，不假定任何工作已完成。 **IMAPIFolder::CopyMessages**可能已经能够邮件复制或移动一个或多个之前遇到错误。 
  
## <a name="see-also"></a>另请参阅



[IMAPIFolder : IMAPIContainer](imapifolderimapicontainer.md)

