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
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 7fec6b6236d26789a3ec9abee7d2ae1c620f89b4
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22593471"
---
# <a name="imapiforminfosaveform"></a>IMAPIFormInfo::SaveForm

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
配置文件中保存窗体特定的说明。
  
```cpp
HRESULT SaveForm(
  LPCSTR szFileName
);
```

## <a name="parameters"></a>参数

 _szFileName_
  
> [in]命名窗体的说明邮件文件及其说明的保存位置的字符串。 此文件名称必须具有.fdm 扩展名。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 呼叫成功或多个预期值返回。
    
MAPI_E_EXTENDED_ERROR 
  
> 无法写入配置文件。 要获取与错误关联的[MAPIERROR](mapierror.md)结构，请调用[IMAPIProp::GetLastError](imapiprop-getlasterror.md)方法。 
    
MAPI_E_NO_SUPPORT 
  
> **SaveForm**称为可能要将表单保存在本地窗体容器。 本地窗体容器上不支持**SaveForm** 。 
    
## <a name="remarks"></a>注解

客户端应用程序调用**IMAPIFormInfo::SaveForm**方法具有给定的文件名的文件中保存当前表单的说明。 **SaveForm**创建一个配置文件。 
  
## <a name="notes-to-callers"></a>给调用方的说明

您可以通过从表单库提供程序显示的窗体描述符消息对话框中的列表中选择联系人重新安装窗体。 窗体描述符消息的建议的扩展名是.fdm。
  
调用[IMAPIProp::GetLastError](imapiprop-getlasterror.md)方法，如果**SaveForm**返回 MAPI_E_EXTENDED_ERROR，并检查返回的**MAPIERROR**结构，以确定导致出错的条件。 
  
## <a name="see-also"></a>另请参阅



[IMAPIProp::GetLastError](imapiprop-getlasterror.md)
  
[MAPIERROR](mapierror.md)
  
[IMAPIFormInfo : IMAPIProp](imapiforminfoimapiprop.md)

