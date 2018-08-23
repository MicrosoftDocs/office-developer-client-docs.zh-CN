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
ms.openlocfilehash: 4e2d4f76fe436fd18b439bbbb558b1169094b438
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22589460"
---
# <a name="imsgstoresetreceivefolder"></a>IMsgStore::SetReceiveFolder

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
为特定邮件类别的传入消息的目标建立一个文件夹。
  
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
  
> [in]指向要与新关联的邮件类的接收文件夹。 如果_lpszMessageClass_参数设置为 NULL 或空字符串， **SetReceiveFolder**设置默认接收消息存储库的文件夹。 
    
 _ulFlags_
  
> [in]位掩码的标志的控制传入的字符串中的文本的类型。 可以设置以下标记：
    
MAPI_UNICODE 
  
> 邮件类字符串采用 Unicode 格式。 如果未设置 MAPI_UNICODE 标志，消息类字符串是 ANSI 格式。
    
 _cbEntryID_
  
> [in]在_lpEntryID_参数指向的项标识符的字节数。 
    
 _lpEntryID_
  
> [in]指向要建立作为接收文件夹的文件夹的项标识符的指针。 如果_lpEntryID_参数设置为 NULL， **SetReceiveFolder**替换当前收到消息存储库的默认文件夹。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 已成功建立的接收文件夹。
    
## <a name="remarks"></a>注解

**IMsgStore::SetReceiveFolder**方法设置或更改为特定邮件类的接收文件夹。 与**SetReceiveFolder**，客户端可以使用连续呼叫指定不同接收每个定义的邮件类的文件夹或指定为所有的多个邮件类的传入消息转到同一文件夹中。 例如，客户端可以有其自己的消息的类到达其自己的文件夹中。 传真应用程序可以指定一个文件夹存储提供程序将在其中放传入传真和提供程序将在其中放传出传真的另一个文件夹。
  
如果**SetReceiveFolder**到在呼叫期间发生错误，接收文件夹设置保持不变。 
  
如果**SetReceiveFolder**更改与_lpEntryID_的接收文件夹设置设置为 NULL，表明应设置默认的接收文件夹、 **SetReceiveFolder**即使出现指示没有现有设置，则返回 S_OK邮件类。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 参考 （英文）

MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**Comment**|
|:-----|:-----|:-----|
|MsgStoreDlg.cpp  <br/> |CMsgStoreDlg::OnSetReceiveFolder  <br/> |MFCMAPI 使用**IMsgStore::SetReceiveFolder**方法将文件夹设置为一个特定的邮件类的接收文件夹。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMsgStore : IMAPIProp](imsgstoreimapiprop.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

