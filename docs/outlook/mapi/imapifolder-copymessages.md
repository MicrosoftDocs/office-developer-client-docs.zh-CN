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
ms.openlocfilehash: 21aa28e1a2c11ee7361fb4921f8d527b3e3ceb44
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33424453"
---
# <a name="imapifoldercopymessages"></a>IMAPIFolder::CopyMessages

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
复制或移动一个或多个邮件。
  
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
  
> [in]指向标识要复制或移动的邮件 [的 ENTRYLIST](entrylist.md) 结构的数组的指针。 
    
 _lpInterface_
  
> [in]指向接口标识符的指针 (IID) 表示用于访问  _lpDestFolder_ 参数指向的目标文件夹的接口。 传递 NULL 会导致服务提供商返回标准文件夹接口 [IMAPIFolder ： IMAPIContainer](imapifolderimapicontainer.md)。 客户端必须传递 NULL。 其他调用方可以将  _lpInterface_ 参数设置为 IID_IUnknown、IID_IMAPIProp、IID_IMAPIContainer 或 IID_IMAPIFolder。 
    
 _lpDestFolder_
  
> [in]一个指向打开文件夹的指针，用于接收复制或移动的邮件。
    
 _ulUIParam_
  
> [in]该方法显示的任何对话框或窗口的父窗口的句柄。 除非客户端在 _ulFlags_ 参数中设置 MESSAGE_DIALOG 标志，并传递 _lpProgress_ 参数中的 NULL，否则将忽略 _ulUIParam_ 参数。 
    
 _lpProgress_
  
> [in]指向显示进度指示器的进度对象的指针。 如果在  _lpProgress_ 中传递 NULL，则邮件存储提供程序使用 MAPI 进度对象实现显示进度指示器。 除非在 _ulFlags_ 中设置了 MESSAGE_DIALOG 标志，否则将忽略 _lpProgress_ 参数。
    
 _ulFlags_
  
> [in]控制复制或移动操作完成方式的标志的位掩码。 可以设置以下标志：
    
MAPI_DECLINE_OK 
  
> 如果邮件存储提供程序通过调用支持对象的 [IMAPISupport：:D oCopyTo](imapisupport-docopyto.md)或 [IMAPISupport：:D oCopyProps](imapisupport-docopyprops.md)方法实现 **IMAPIFolder：：CopyMessages，** 则通知其立即返回 MAPI_E_DECLINE_COPY。 
    
MESSAGE_DIALOG 
  
> 在操作继续时显示进度指示器。
    
MESSAGE_MOVE 
  
> 要移动而不是复制邮件。 如果未MESSAGE_MOVE，则复制邮件。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功复制或移动一个或多个邮件。
    
MAPI_E_DECLINE_COPY 
  
> 提供程序通过调用支持对象方法来实现此方法，并且调用方已传递MAPI_DECLINE_OK标志。
    
MAPI_W_PARTIAL_COMPLETION 
  
> 调用成功，但并非所有条目都已成功复制或移动。 返回此警告时，应成功处理呼叫。 若要测试此警告，请使用 **HR_FAILED** 宏。 有关详细信息，请参阅使用 [宏处理错误](using-macros-for-error-handling.md)。
    
## <a name="remarks"></a>备注

**IMAPIFolder：：CopyMessages** 方法将邮件复制或移动到另一个文件夹。 
  
使用读/写权限打开的邮件可以移动或复制。 
  
## <a name="notes-to-implementers"></a>针对实现者的说明

如果要在未使用[IMAPISupport：：CopyMessages](imapisupport-copymessages.md)方法的情况下将邮件复制到其他邮件存储，则必须先调用设置了 GENERATE_RECEIPT_ONLY 标志的[IMAPIFolder：：SetReadFlags。](imapifolder-setreadflags.md) 接收邮件存储不负责为复制或移动的邮件生成读取报告。 如果要调用 **IMAPISupport：：CopyMessages** 来实现 **IMAPIFolder：：CopyMessages，** 请不要调用 **SetReadFlags**;MAPI 将调用它。 
  
你的实现可以按任何顺序移动或复制邮件，并按任何顺序生成读取状态报告。 也就是说，您可以在生成任何已读状态报告之前完成邮件复制，或在实现开始复制操作之前发送报告。 但是，应为要复制的所有邮件发送阅读报告，而不管复制是否成功。
  
当复制或移动操作涉及多条消息时，请尽可能完全执行该操作。 除非发生超出你的控制范围（如内存不足、磁盘空间不足或邮件存储损坏）发生的故障，否则不要提前停止操作。
  
尝试跨移动或复制操作维护条目标识符。 您还应该保留条目标识符，尽管这不是必需的。
  
在移动或复制邮件时发送通知，以便客户端预想其对消息 [的 IMAPIProp：：SaveChanges](imapiprop-savechanges.md) 方法的调用可能会失败。 
  
请勿在复制或移动操作中包括邮件的状态。 移动或复制邮件状态会大大影响性能。
  
## <a name="notes-to-callers"></a>给调用方的说明

使用 **IMAPIFolder：：CopyMessages** 填充搜索结果文件夹，其中邮件通常按父文件夹进行分组。 
  
预计以下情况下会返回这些值。
  
|**Condition**|**返回值**|
|:-----|:-----|
|**IMAPIFolder：：CopyMessages** 已成功复制或移动每封邮件。  <br/> |S_OK  <br/> |
|**IMAPIFolder：：CopyMessages** 无法成功复制或移动每条消息。  <br/> |MAPI_W_PARTIAL_COMPLETION  <br/> |
|**IMAPIFolder：：CopyMessages** 无法完成。  <br/> |任何错误值  <br/> |
   
当 **IMAPIFolder：：CopyMessages** 无法完成时，不要假定未完成任何工作。 **IMAPIFolder：：CopyMessages** 可能能够在遇到错误之前复制或移动一个或多个消息。 
  
## <a name="see-also"></a>另请参阅



[IMAPIFolder : IMAPIContainer](imapifolderimapicontainer.md)

