---
title: IMsgStoreSetReceiveFolder
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMsgStore.SetReceiveFolder
api_type:
- COM
ms.assetid: 469f0412-1343-47ce-b6e8-e0d5e56c29bb
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: efa5d60098fd5f16328669249a8445a124d9878b
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33434086"
---
# <a name="imsgstoresetreceivefolder"></a>IMsgStore::SetReceiveFolder

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
建立一个文件夹作为特定邮件类的传入邮件的目标。
  
```cpp
HRESULT SetReceiveFolder(
  LPSTR lpszMessageClass,
  ULONG ulFlags,
  ULONG cbEntryID,
  LPENTRYID lpEntryID
);
```

## <a name="parameters"></a>参数

 _lpszMessageClass_
  
> [in]指向要与新接收文件夹关联的邮件类的指针。 如果  _lpszMessageClass_ 参数设置为 NULL 或空字符串 **，SetReceiveFolder** 将设置邮件存储的默认接收文件夹。 
    
 _ulFlags_
  
> [in]控制传入字符串中的文本类型的标志位掩码。 可以设置以下标志：
    
MAPI_UNICODE 
  
> 邮件类字符串采用 Unicode 格式。 如果未MAPI_UNICODE，则邮件类字符串采用 ANSI 格式。
    
 _cbEntryID_
  
> [in]  _lpEntryID_ 参数指向的条目标识符中的字节计数。 
    
 _lpEntryID_
  
> [in]指向要建立为接收文件夹的文件夹的条目标识符的指针。 如果  _lpEntryID_ 参数设置为 **NULL，SetReceiveFolder** 将当前接收文件夹替换为邮件存储的默认值。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功建立接收文件夹。
    
## <a name="remarks"></a>备注

**IMsgStore：：SetReceiveFolder** 方法设置或更改特定邮件类的接收文件夹。 使用 **SetReceiveFolder，** 客户端可以通过连续调用为每个已定义邮件类指定不同的接收文件夹，或指定多个邮件类的传入邮件都转到同一文件夹。 例如，客户端可以有自己的邮件类别到达其自己的文件夹中。 传真应用程序可以指定一个文件夹，其中存储提供程序将传入传真放在其中，另一个文件夹由提供商将传出传真放在其中。
  
如果在调用 **SetReceiveFolder** 期间发生错误，则接收文件夹设置保持不变。 
  
如果 **SetReceiveFolder** 更改接收文件夹设置，  _将 lpEntryID_ 设置为 NULL，指示应设置默认接收文件夹， **则 SetReceiveFolder** 将返回 S_OK即使指示的邮件类没有现有设置。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|MsgStoreDlg.cpp  <br/> |CMsgStoreDlg：：OnSetReceiveFolder  <br/> |MFCMAPI 使用 **IMsgStore：：SetReceiveFolder** 方法将文件夹设置为特定邮件类的接收文件夹。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMsgStore : IMAPIProp](imsgstoreimapiprop.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

