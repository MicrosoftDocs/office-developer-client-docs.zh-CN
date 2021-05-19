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
ms.openlocfilehash: ab21dcfb9011b675e3db4e4df29cb6ecafa6e7c6
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33435346"
---
# <a name="imsgstoregetreceivefolder"></a>IMsgStore::GetReceiveFolder

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
获取已建立为指定邮件类的传入邮件的目标或作为邮件存储的默认接收文件夹的文件夹。
  
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
  
> [in]指向与接收文件夹关联的邮件类的指针。 如果  _lpszMessageClass_ 参数设置为 NULL 或空字符串 **，GetReceiveFolder** 将返回邮件存储的默认接收文件夹。 
    
 _ulFlags_
  
> [in]控制传入和返回的字符串类型的标志位掩码。 可以设置以下标志：
    
MAPI_UNICODE 
  
> 邮件类字符串采用 Unicode 格式。 如果未MAPI_UNICODE，则邮件类字符串采用 ANSI 格式。
    
 _lpcbEntryID_
  
> [out]指向  _lppEntryID_ 参数指向的条目标识符中的字节计数的指针。 
    
 _lppEntryID_
  
> [out]指向指向所请求接收文件夹的条目标识符的指针的指针。
    
 _lppszExplicitClass_
  
> [out]指向显式将  _lppEntryID_ 指向的文件夹作为接收文件夹的邮件类的指针的指针。 此消息类应该与  _lpszMessageClass_ 参数中的类相同，或者是该类的基类。 传递 NULL 表示  _lppEntryID_ 指向的文件夹是邮件存储的默认接收文件夹。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功返回接收文件夹。
    
## <a name="remarks"></a>备注

**IMsgStore：：GetReceiveFolder** 方法获取接收文件夹的条目标识符，该文件夹被指定为接收特定邮件类的传入邮件。 呼叫者可以在  _lpszMessageClass_ 参数中指定邮件类或 NULL。 如果  _lpszMessageClass_ 为 **NULL，GetReceiveFolder** 将返回以下值： 
  
- 在  _lppszExplicitClass_ 中，由明确设置接收文件夹的  _lpszMessageClass_ 指向的邮件类的第一个基类的名称。 
    
- 在  _lppEntryID_ 中  _，lppszExplicitClass_ 参数指向的基类的接收文件夹的条目标识符。 
    
例如，假设邮件类 IPM 的接收 **文件夹。Note** has been set to the entry identifier of the Inbox and **GetReceiveFolder** is called with the contents of _lpszMessageClass_ set to **IPM.注意。电话**。 如果 **为 IPM。注意。电话** 没有显式接收文件夹集 **，GetReceiveFolder** 返回 _lppEntryID_ 和 IPM 中收件箱的 **条目标识符。** _lppszExplicitClass_ 中的注释。
  
如果客户端为邮件类调用 **GetReceiveFolder，** 并且尚未为邮件类设置接收文件夹，  _则 lppszExplicitClass_ 可以是零长度字符串、Unicode 格式的字符串或 ANSI 格式的字符串，具体取决于客户端是否在  _ulFlags_ 参数中设置 MAPI_UNICODE 标志。 
  
通过传递  _lpszMessageClass_ 参数中的 NULL 获取的默认接收文件夹始终存在于每个邮件存储中。 
  
使用 _lppEntryID_ 中返回的条目标识符完成时，客户端应调用 [MAPIFreeBuffer](mapifreebuffer.md)函数，以释放保留该条目标识符的内存。 当使用 _lppszExplicitClass_ 中返回的邮件类字符串完成时，它还应调用 **MAPIFreeBuffer** 以释放包含该字符串的内存。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|MAPIFunctions.cpp  <br/> |GetInbox  <br/> |MFCMAPI 使用 **IMsgStore：：GetReceiveFolder** 方法来查找"收件箱"文件夹。  <br/> |
   
## <a name="see-also"></a>另请参阅



[MAPIFreeBuffer](mapifreebuffer.md)
  
[IMsgStore : IMAPIProp](imsgstoreimapiprop.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

