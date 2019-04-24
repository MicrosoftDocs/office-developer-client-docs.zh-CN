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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32348774"
---
# <a name="imsgstoregetreceivefolder"></a>IMsgStore::GetReceiveFolder

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
获取作为指定邮件类别的传入邮件的目标或作为邮件存储的默认接收文件夹而建立的文件夹。
  
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
  
> 实时指向与接收文件夹相关联的邮件类的指针。 如果将_lpszMessageClass_参数设置为 NULL 或空字符串, 则**GetReceiveFolder**将返回邮件存储区的默认接收文件夹。 
    
 _ulFlags_
  
> 实时标志的位掩码, 用于控制传入和返回的字符串的类型。 可以设置以下标志:
    
MAPI_UNICODE 
  
> 邮件类字符串采用 Unicode 格式。 如果未设置 MAPI_UNICODE 标志, 则邮件类字符串将采用 ANSI 格式。
    
 _lpcbEntryID_
  
> 排除指向条目标识符中由_lppEntryID_参数指向的字节计数的指针。 
    
 _lppEntryID_
  
> 排除指向所请求的接收文件夹的条目标识符的指针的指针。
    
 _lppszExplicitClass_
  
> 排除指向邮件类的指针的指针, 该邮件类显式设置为其接收文件夹由_lppEntryID_指向的文件夹。 此邮件类应与_lpszMessageClass_参数中的类相同, 或与该类的基类相同。 传递 NULL 表示_lppEntryID_指向的文件夹是邮件存储的默认接收文件夹。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功返回接收文件夹。
    
## <a name="remarks"></a>注解

**IMsgStore:: GetReceiveFolder**方法获取接收文件夹的条目标识符, 该文件夹是指定用于接收特定邮件类别的传入邮件的文件夹。 调用方可以在_lpszMessageClass_参数中指定邮件类或 NULL。 如果_lpszMessageClass_为 NULL, 则**GetReceiveFolder**将返回以下值: 
  
- 在_lppszExplicitClass_中, 由_lpszMessageClass_指向的邮件类的第一个基类的名称, 该基类显式设置接收文件夹。 
    
- 在_lppEntryID_中, 由_lppszExplicitClass_参数指向的基类的接收文件夹的条目标识符。 
    
例如, 假设邮件类为 IPM 的接收文件夹 **。注意**已设置为收件箱的条目标识符, 并且将使用设置为 IPM 的_lpszMessageClass_的内容调用**GetReceiveFolder** **。注意**: "电话"。 如果**IPM。注意: 电话**未设置显式接收文件夹, **GetReceiveFolder**返回_lppEntryID_和 IPM 中的收件箱的条目标识符 **。注意**在_lppszExplicitClass_中。
  
如果客户端为邮件类调用**GetReceiveFolder** , 但尚未为该邮件类别设置接收文件夹, 则_lppszExplicitClass_可以是零长度字符串、Unicode 格式的字符串, 也可以是 ANSI 格式的字符串, 具体取决于是否client 在_ulFlags_参数中设置 MAPI_UNICODE 标志。 
  
通过在_lpszMessageClass_参数中传递 NULL 获取的默认接收文件夹, 对于每个邮件存储始终存在。 
  
在使用_lppEntryID_中返回的条目标识符完成时, 客户端应调用[MAPIFreeBuffer](mapifreebuffer.md)函数, 以释放保留该条目标识符的内存。 在使用_lppszExplicitClass_中返回的邮件类字符串完成时, 它还应调用**MAPIFreeBuffer** , 以释放保留该字符串的内存。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|MAPIFunctions  <br/> |GetInbox  <br/> |MFCMAPI 使用**IMsgStore:: GetReceiveFolder**方法查找 "收件箱" 文件夹。  <br/> |
   
## <a name="see-also"></a>另请参阅



[MAPIFreeBuffer](mapifreebuffer.md)
  
[IMsgStore : IMAPIProp](imsgstoreimapiprop.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

