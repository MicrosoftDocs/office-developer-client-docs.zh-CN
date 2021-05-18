---
title: IMAPIFormMgrOpenFormContainer
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IMAPIFormMgr.OpenFormContainer
api_type:
- COM
ms.assetid: df02bdc5-903a-4ce2-9f43-5f4513ea19b3
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 68a358c91e35c5a075e220794c78f4e5c96e43ee
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32321635"
---
# <a name="imapiformmgropenformcontainer"></a>IMAPIFormMgr::OpenFormContainer

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
打开特定表单容器的 [IMAPIFormContainer](imapiformcontaineriunknown.md) 接口。 
  
```cpp
HRESULT OpenFormContainer(
  HFRMREG hfrmreg,
  LPUNKNOWN lpunk,
  LPMAPIFORMCONTAINER FAR * lppfcnt
);
```

## <a name="parameters"></a>参数

 _分贝区_
  
> [in]指示要打开的表单库的 (，即要打开表单的表单容器的) 。 一个特定于表单库提供程序的枚举。 可能的FCRMREG 值包括：
    
HFRMREG_DEFAULT 
  
> 方便的表单容器。
    
HFRMREG_FOLDER 
  
> 文件夹容器。 
    
HFRMREG_PERSONAL 
  
> 默认邮件存储的容器。 
    
HFRMREG_LOCAL 
  
> 本地表单容器。 
    
 _lpunk_
  
> [in]指向打开接口的对象的指针。 _lpunk_ 参数必须为 **null，** 除非 _用于该设置的参数的值_ 需要对象指针。 
    
 _lppfcnt_
  
> [out]指向返回的表单容器对象的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 调用成功并返回了预期值。
    
MAPI_E_NO_INTERFACE 
  
> _lpunk_ 指向的对象不支持所需的接口。 
    
## <a name="remarks"></a>备注

表单查看器调用 **IMAPIFormMgr：：OpenFormContainer** 方法来打开特定表单容器的 **IMAPIFormContainer** 接口。 然后，此接口可用于将表单安装到表单容器以及从表单容器中删除表单。 
  
## <a name="notes-to-callers"></a>给调用方的说明

如果  _HFRMREG_FOLDER_ 中的值为  _HFRMREG_FOLDER，则 lpunk_ 中使用的接口标识符必须为非 **null，** 并且必须允许 [IUnknown：：QueryInterface](https://msdn.microsoft.com/library/ms682521%28v=VS.85%29.aspx) 方法调用 [IMAPIFolder](imapifolderimapicontainer.md) 接口。 
  
若要打开本地表单容器，必须使用 **对 OpenFormContainer** 方法或 [MAPIOpenLocalFormContainer](mapiopenlocalformcontainer.md) 函数的调用;不能使用 [IMAPIFormMgr：：SelectFormContainer](imapiformmgr-selectformcontainer.md) 方法使用户可以选择本地表单容器。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|MainDlg.cpp  <br/> |CMainDlg：：OnOpenFormContainer  <br/> |MFCMAPI 使用 **IMAPIFormMgr：：OpenFormContainer** 方法来检索表单容器，以便可以呈现容器的内容。  <br/> |
|MsgStoreDlg.cpp  <br/> |CMsgStoreDlg：：OnOpenFormContainer  <br/> |MFCMAPI 使用 **IMAPIFormMgr：：OpenFormContainer** 方法检索文件夹的表单容器，以便可以呈现容器的内容。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPIFormContainer::InstallForm](imapiformcontainer-installform.md)
  
[IMAPIFormMgr::SelectFormContainer](imapiformmgr-selectformcontainer.md)
  
[MAPIOpenLocalFormContainer](mapiopenlocalformcontainer.md)
  
[IMAPIFormMgr : IUnknown](imapiformmgriunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

