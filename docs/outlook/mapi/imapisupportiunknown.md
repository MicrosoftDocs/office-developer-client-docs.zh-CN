---
title: IMAPISupport IUnknown
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPISupport
api_type:
- COM
ms.assetid: 92bfe604-18dd-46a1-9ae8-0b04167606bd
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 6da488408d3be9464d6ae1e016d5095707d451e4
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33415437"
---
# <a name="imapisupport--iunknown"></a>IMAPISupport : IUnknown

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
提供通常由服务提供程序和邮件服务入口点函数执行的任务的实现。 当 MAPI 调用其提供程序对象的登录方法时, 服务提供程序将收到指向其支持对象的指针。 邮件服务在对其入口点函数的调用中接收其支持对象指针。
  
|||
|:-----|:-----|
|标头文件：  <br/> |Mapispi  <br/> |
|公开者:  <br/> |支持对象  <br/> |
|实现者：  <br/> |MAPI  <br/> |
|调用者：  <br/> |服务提供程序  <br/> |
|接口标识符:  <br/> |IID_IMAPISup  <br/> |
|指针类型:  <br/> |LPMAPISUP  <br/> |
   
## <a name="vtable-order"></a>Vtable 顺序

|||
|:-----|:-----|
|[GetLastError](imapisupport-getlasterror.md) <br/> |返回一个[MAPIERROR](mapierror.md)结构, 该结构包含上一个支持对象错误的相关信息。  <br/> |
|[GetMemAllocRoutines](imapisupport-getmemallocroutines.md) <br/> |检索 MAPI 内存分配和释放函数的地址 ([MAPIAllocateBuffer](mapiallocatebuffer.md)、 [MAPIAllocateMore](mapiallocatemore.md)和[MAPIFreeBuffer](mapifreebuffer.md))。  <br/> |
|[订阅](imapisupport-subscribe.md) <br/> |注册通知接收器以通过 MAPI 接收通知。  <br/> |
|[取消订阅](imapisupport-unsubscribe.md) <br/> |取消发送以前通过呼叫**订阅**方法建立的通知的责任。  <br/> |
|[Notify](imapisupport-notify.md) <br/> |将指定事件的通知发送到最初通过**订阅**方法注册通知的通知源。  <br/> |
|[ModifyStatusRow](imapisupport-modifystatusrow.md) <br/> |通过添加新行或修改现有行来修改状态表。  <br/> |
|[OpenProfileSection](imapisupport-openprofilesection.md) <br/> |打开当前配置文件的一部分, 并返回一个[IProfSect](iprofsectimapiprop.md)指针以供进一步访问  <br/> |
|[RegisterPreprocessor](imapisupport-registerpreprocessor.md) <br/> |注册传输提供程序的预处理器函数 (符合[PreprocessMessage](preprocessmessage.md)原型的函数)。  <br/> |
|[NewUID](imapisupport-newuid.md) <br/> |创建要用作唯一标识符的新[MAPIUID](mapiuid.md)结构。  <br/> |
|[MakeInvalid](imapisupport-makeinvalid.md) <br/> |将对象标记为不可用。  <br/> |
|[SpoolerYield](imapisupport-spooleryield.md) <br/> |将 CPU 的控制提供给 MAPI 后台处理程序, 以便它可以执行必要的任何任务。  <br/> |
|[SpoolerNotify](imapisupport-spoolernotify.md) <br/> |通知 MAPI 后台处理程序的状态更改或服务请求。  <br/> |
|[CreateOneOff](imapisupport-createoneoff.md) <br/> |为一次性地址创建条目标识符。  <br/> |
|[SetProviderUID](imapisupport-setprovideruid.md) <br/> |注册唯一表示服务提供程序的**MAPIUID**结构。  <br/> |
|[CompareEntryIDs](imapisupport-compareentryids.md) <br/> |对两个条目标识符进行比较, 以确定它们是否引用同一个对象。  <br/> |
|[OpenTemplateID](imapisupport-opentemplateid.md) <br/> |打开外部通讯簿提供程序中的收件人条目。  <br/> |
|[OpenEntry](imapisupport-openentry.md) <br/> |打开一个对象并返回一个接口指针以供进一步访问。  <br/> |
|[GetOneOffTable](imapisupport-getoneofftable.md) <br/> |返回指向 MAPI 一次性表 (所有通讯簿提供程序为创建新收件人所支持的模板列表) 的指针。  <br/> |
|[地址](imapisupport-address.md) <br/> |显示 "常用地址" 对话框。  <br/> |
|[详细信息](imapisupport-details.md) <br/> |显示一个对话框, 显示有关特定通讯簿条目的详细信息。  <br/> |
|[NewEntry](imapisupport-newentry.md) <br/> |将新的收件人直接添加到通讯簿容器或传出邮件的收件人列表中。  <br/> |
|[DoConfigPropsheet](imapisupport-doconfigpropsheet.md) <br/> |显示配置属性表。  <br/> |
|[CopyMessages](imapisupport-copymessages.md) <br/> |将邮件从一个文件夹复制或移动到另一个文件夹。  <br/> |
|[CopyFolder](imapisupport-copyfolder.md) <br/> |将文件夹从其当前父文件夹复制或移动到另一个父文件夹。  <br/> |
|[DoCopyTo](imapisupport-docopyto.md) <br/> |将一个对象的所有属性 (特别排除的属性除外) 复制或移动到另一个对象。  <br/> |
|[DoCopyProps](imapisupport-docopyprops.md) <br/> |将对象的一个或多个属性复制或移动到另一个对象。  <br/> |
|[DoProgressDialog](imapisupport-doprogressdialog.md) <br/> |检索显示进度指示器的进度对象。  <br/> |
|[ReadReceipt](imapisupport-readreceipt.md) <br/> |生成邮件的读取或未读报告。  <br/> |
|[PrepareSubmit](imapisupport-preparesubmit.md) <br/> |准备邮件以提交到 MAPI 后台处理程序。  <br/> |
|[ExpandRecips](imapisupport-expandrecips.md) <br/> |完成邮件的收件人列表, 展开特定的通讯组列表。  <br/> |
|[DoSentMail](imapisupport-dosentmail.md) <br/> |处理已发送的邮件。  <br/> |
|[OpenAddressBook](imapisupport-openaddressbook.md) <br/> |提供对通讯簿的访问权限。  <br/> |
|[CompleteMsg](imapisupport-completemsg.md) <br/> |对邮件执行后处理。  <br/> |
|[StoreLogoffTransports](imapisupport-storelogofftransports.md) <br/> |请求邮件存储的有序释放。  <br/> |
|[StatusRecips](imapisupport-statusrecips.md) <br/> |生成传递和 nondelivery 报告。  <br/> |
|[WrapStoreEntryID](imapisupport-wrapstoreentryid.md) <br/> |将邮件存储区的内部条目标识符转换为 MAPI 标准格式的条目标识符。  <br/> |
|[ModifyProfile](imapisupport-modifyprofile.md) <br/> |对邮件存储库配置文件部分进行永久性更改。  <br/> |
|[IStorageFromStream](imapisupport-istoragefromstream.md) <br/> |实现存储对象以访问流。  <br/> |
|[GetSvcConfigSupportObj](imapisupport-getsvcconfigsupportobj.md) <br/> |创建邮件服务支持对象。  <br/> |
   
## <a name="remarks"></a>说明

通讯簿、邮件存储、传输提供程序和邮件服务都有其自己的支持对象。 服务提供程序和邮件服务将其支持对象中的方法作为其他接口方法实现的一部分调用。 每个不同的支持对象都具有应用于其调用方的方法的完整实现;不适用的方法返回 MAPI_E_NO_SUPPORT。 通讯簿提供程序支持对象具有以下方法的实现:
  
||||
|:-----|:-----|:-----|
|**地址** <br/> |**CompareEntryIDs** <br/> |**CreateOneOff** <br/> |
|**详细信息** <br/> |**DoConfigPropsheet** <br/> |**DoProgressDialog** <br/> |
|**GetLastError** <br/> |**GetMemAllocRoutines** <br/> |**GetOneOffTable** <br/> |
|**IStorageFromStream** <br/> |**GetSvcConfigSupportObj** <br/> |**MakeInvalid** <br/> |
|**ModifyStatusRow** <br/> |**NewEntry** <br/> |**NewUID** <br/> |
|**Notify** <br/> |**OpenAddressBook** <br/> |**OpenEntry** <br/> |
|**OpenProfileSection** <br/> |**OpenTemplateID** <br/> |**SetProviderUID** <br/> |
|**订阅** <br/> |**取消订阅** <br/> |**WrapStoreEntryID** <br/> |
   
邮件存储区提供程序支持对象具有以下方法的实现:
  
||||
|:-----|:-----|:-----|
|**CompareEntryIDs** <br/> |**CompleteMsg** <br/> |**CopyFolder** <br/> |
|**CopyMessages** <br/> |**CreateOneOff** <br/> |**DoCopyProps** <br/> |
|**DoCopyTo** <br/> |**DoConfigPropsheet** <br/> |**DoProgressDialog** <br/> |
|**DoSentMail** <br/> |**ExpandRecips** <br/> |**GetLastError** <br/> |
|**GetMemAllocRoutines** <br/> |**GetSvcConfigSupportObj** <br/> |**MakeInvalid** <br/> |
|**IStorageFromStream** <br/> |**ModifyProfile** <br/> |**ModifyStatusRow** <br/> |
|**NewUID** <br/> |**Notify** <br/> |**OpenAddressBook** <br/> |
|**OpenEntry** <br/> |**OpenProfileSection** <br/> |**PrepareSubmit** <br/> |
|**ReadReceipt** <br/> |**SetProviderUID** <br/> |**SpoolerNotify** <br/> |
|**StoreLogoffTransports** <br/> |**订阅** <br/> |**取消订阅** <br/> |
|**WrapStoreEntryID** <br/> |
   
传输提供程序支持对象具有以下方法的实现:
  
||||
|:-----|:-----|:-----|
|**DoConfigPropsheet** <br/> |**CompareEntryIDs** <br/> |**CreateOneOff** <br/> |
|**GetMemAllocRoutines** <br/> |**GetSvcConfigSupportObj** <br/> |**GetLastError** <br/> |
|**IStorageFromStream** <br/> |**MakeInvalid** <br/> |**ModifyStatusRow** <br/> |
|**OpenAddressBook** <br/> |**RegisterPreprocessor** <br/> |**NewUID** <br/> |
|**Notify** <br/> |**OpenProfileSection** <br/> |**OpenEntry** <br/> |
|**StatusRecips** <br/> |**SpoolerNotify** <br/> |**SpoolerYield** <br/> |
|**WrapStoreEntryID** <br/> |**订阅** <br/> |**取消订阅** <br/> |
   
邮件服务支持对象具有以下方法的实现:
  
|||
|:-----|:-----|
|**DoConfigPropsheet** <br/> |**GetLastError** <br/> |
|**GetMemAllocRoutines** <br/> |**GetSvcConfigSupportObj** <br/> |
|**MakeInvalid** <br/> |**NewUID** <br/> |
|**OpenProfileSection** <br/> |
   
## <a name="see-also"></a>另请参阅



[MAPI 接口](mapi-interfaces.md)

