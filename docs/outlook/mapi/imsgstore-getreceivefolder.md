---
title: IMsgStoreGetReceiveFolder
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMsgStore.GetReceiveFolder
api_type:
- COM
ms.assetid: ccd9d623-a3cb-4e66-9649-78c3887cb726
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: a8cd211cc16b620ac47357271070e0b45b867bea
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22579940"
---
# <a name="imsgstoregetreceivefolder"></a>IMsgStore::GetReceiveFolder

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
获取时，传入邮件指定的邮件类的或为默认的目标接收的消息存储库文件夹建立的文件夹。
  
```cpp
HRESULT GetReceiveFolder(
  LPSTR lpszMessageClass,
  ULONG ulFlags,
  ULONG FAR * lpcbEntryID,
  LPENTRYID FAR * lppEntryID,
  LPSTR FAR * lppszExplicitClass
);
```

## <a name="parameters"></a>参数

 _lpszMessageClass_
  
> [in]指向相关联的接收文件夹的邮件类的指针。 如果_lpszMessageClass_参数设置为 NULL 或空字符串， **GetReceiveFolder**返回默认接收消息存储库的文件夹。 
    
 _ulFlags_
  
> [in]位掩码的标志的控制的传入的和返回字符串的类型。 可以设置以下标记：
    
MAPI_UNICODE 
  
> 邮件类字符串采用 Unicode 格式。 如果未设置 MAPI_UNICODE 标志，消息类字符串是 ANSI 格式。
    
 _lpcbEntryID_
  
> [输出]一个指向_lppEntryID_参数指向该条目标识符中的字节数。 
    
 _lppEntryID_
  
> [输出]为请求的项标识符指针的指针接收文件夹。
    
 _lppszExplicitClass_
  
> [输出]指向作为显式设置的邮件类的指针的指针其接收由_lppEntryID_文件夹指向的文件夹。 此邮件类也应在_lpszMessageClass_参数中的类或该类的基类相同。 传递 NULL 指示由_lppEntryID_指向的文件夹是默认接收的消息存储库文件夹。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功返回的接收文件夹。
    
## <a name="remarks"></a>注解

**IMsgStore::GetReceiveFolder**方法获取接收文件夹中，指定要接收传入邮件的特定邮件类别的文件夹的项标识符。 呼叫者可以_lpszMessageClass_参数中指定的邮件类或 NULL。 如果_lpszMessageClass_为 NULL，则**GetReceiveFolder**将返回以下值： 
  
- _LppszExplicitClass_中的第一个基类的邮件类的名称指向_lpszMessageClass_显式设置的接收文件夹。 
    
- _LppEntryID_中的项标识符的接收文件夹的基类指向_lppszExplicitClass_参数。 
    
例如，假设邮件类**IPM 的接收文件夹。注意**已设置的项标识符的收件箱和**GetReceiveFolder**称为_lpszMessageClass_设置为**IPM 的内容。Note.Phone**。 如果**IPM。Note.Phone**不具有显式接收文件夹集， **GetReceiveFolder** _lppEntryID_和**IPM 中返回的项标识符的收件箱。注意** _lppszExplicitClass_中。
  
如果客户端调用**GetReceiveFolder**为邮件类，并且未设置用于该邮件类的接收文件夹， _lppszExplicitClass_是零长度字符串、 Unicode 格式的字符串或具体取决于 ANSI 格式的字符串客户端_ulFlags_参数中设置 MAPI_UNICODE 标志。 
  
默认的接收文件夹，获取_lpszMessageClass_参数中传递 NULL，每个邮件存储始终存在。 
  
客户端应调用[MAPIFreeBuffer](mapifreebuffer.md)函数完成_lppEntryID_以释放内存，保存该条目标识符中返回的项标识符。 完成使用_lppszExplicitClass_以释放内存包含该字符串中返回的消息类字符串，它还应调用**MAPIFreeBuffer** 。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 参考 （英文）

MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**Comment**|
|:-----|:-----|:-----|
|MAPIFunctions.cpp  <br/> |GetInbox  <br/> |MFCMAPI 使用**IMsgStore::GetReceiveFolder**方法找到收件箱文件夹。  <br/> |
   
## <a name="see-also"></a>另请参阅



[MAPIFreeBuffer](mapifreebuffer.md)
  
[IMsgStore : IMAPIProp](imsgstoreimapiprop.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

