---
title: IMAPIFormInfoSaveForm
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIFormInfo.SaveForm
api_type:
- COM
ms.assetid: 18a10f14-0795-4d4d-b590-f4cef4f2902a
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 391ea3ef4f44db2a9d007241232f58db27647ba2
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33428744"
---
# <a name="imapiforminfosaveform"></a>IMAPIFormInfo::SaveForm

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
将特定表单的说明保存在配置文件中。
  
```cpp
HRESULT SaveForm(
  LPCSTR szFileName
);
```

## <a name="parameters"></a>参数

 _szFileName_
  
> [in]一个字符串，用于命名保存其说明的表单的说明邮件文件。 此文件名必须具有 .fdm 扩展名。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功并返回了预期值。
    
MAPI_E_EXTENDED_ERROR 
  
> 无法写入配置文件。 若要获取与 [错误关联的 MAPIERROR](mapierror.md) 结构，请调用 [IMAPIProp：：GetLastError](imapiprop-getlasterror.md) 方法。 
    
MAPI_E_NO_SUPPORT 
  
> **可能调用 SaveForm** 以将窗体保存在本地窗体容器中。 **本地表单容器不支持 SaveForm。** 
    
## <a name="remarks"></a>备注

客户端应用程序调用 **IMAPIFormInfo：：SaveForm** 方法，将当前表单的说明保存在具有给定文件名的文件中。 **SaveForm** 创建配置文件。 
  
## <a name="notes-to-callers"></a>给调用方的说明

可以通过从表单库提供程序显示的对话框中的表单描述符消息列表中选择表单来重新安装表单。 表单描述符消息的建议扩展为 .fdm。
  
如果 **SaveForm** 返回 MAPI_E_EXTENDED_ERROR，则调用 [IMAPIProp：：GetLastError](imapiprop-getlasterror.md)方法，并检查返回的 **MAPIERROR** 结构以确定导致错误的条件。 
  
## <a name="see-also"></a>另请参阅



[IMAPIProp::GetLastError](imapiprop-getlasterror.md)
  
[MAPIERROR](mapierror.md)
  
[IMAPIFormInfo : IMAPIProp](imapiforminfoimapiprop.md)

