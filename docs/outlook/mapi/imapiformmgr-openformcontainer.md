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
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25393115"
---
# <a name="imapiformmgropenformcontainer"></a>IMAPIFormMgr::OpenFormContainer

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
打开特定窗体容器[IMAPIFormContainer](imapiformcontaineriunknown.md)界面。 
  
```cpp
HRESULT OpenFormContainer(
  HFRMREG hfrmreg,
  LPUNKNOWN lpunk,
  LPMAPIFORMCONTAINER FAR * lppfcnt
);
```

## <a name="parameters"></a>参数

 _hfrmreg_
  
> [in]HFRMREG 枚举指示要打开的窗体库 （也就是说，表单容器来打开）。 HFRMREG 枚举是特定于窗体库提供程序的枚举。 可能 HFRMREG 值包括：
    
HFRMREG_DEFAULT 
  
> 一种方便的窗体容器。
    
HFRMREG_FOLDER 
  
> 文件夹的容器。 
    
HFRMREG_PERSONAL 
  
> 默认的邮件存储的容器。 
    
HFRMREG_LOCAL 
  
> 本地窗体的容器。 
    
 _lpunk_
  
> [in]指向为其打开接口的对象的指针。 _Lpunk_参数必须为**空**，除非_hfrmreg_参数的值需要对象指针。 
    
 _lppfcnt_
  
> [输出]指向返回窗体容器对象的指针的指针。
    
## <a name="return-value"></a>返回值

S_OK 
  
> 呼叫成功或多个预期值返回。
    
MAPI_E_NO_INTERFACE 
  
> 指向_lpunk_对象不支持所需的接口。 
    
## <a name="remarks"></a>说明

表单查看器调用**IMAPIFormMgr::OpenFormContainer**方法打开特定窗体容器**IMAPIFormContainer**接口。 此接口然后可用于安装窗体插入和移除表单从窗体容器。 
  
## <a name="notes-to-callers"></a>给调用方的说明

如果_hfrmreg_中的值，HFRMREG_FOLDER _lpunk_中使用该接口的标识符必须非**null** ，并且必须允许[IMAPIFolder](imapifolderimapicontainer.md)接口[IUnknown::QueryInterface](https://msdn.microsoft.com/library/ms682521%28v=VS.85%29.aspx)方法调用。 
  
若要打开本地窗体容器，必须使用调用**OpenFormContainer**方法或[MAPIOpenLocalFormContainer](mapiopenlocalformcontainer.md)函数中;不能使用[IMAPIFormMgr::SelectFormContainer](imapiformmgr-selectformcontainer.md)方法以使用户能够选择本地窗体容器。 
  
## <a name="mfcmapi-reference"></a>MFCMAPI 引用

有关 MFCMAPI 示例代码，请参阅下表。
  
|**文件**|**函数**|**备注**|
|:-----|:-----|:-----|
|MainDlg.cpp  <br/> |CMainDlg::OnOpenFormContainer  <br/> |MFCMAPI 使用**IMAPIFormMgr::OpenFormContainer**方法检索的窗体容器，因此可以呈现容器的内容。  <br/> |
|MsgStoreDlg.cpp  <br/> |CMsgStoreDlg::OnOpenFormContainer  <br/> |MFCMAPI 使用**IMAPIFormMgr::OpenFormContainer**方法检索的文件夹的窗体容器，因此可以呈现容器的内容。  <br/> |
   
## <a name="see-also"></a>另请参阅



[IMAPIFormContainer::InstallForm](imapiformcontainer-installform.md)
  
[IMAPIFormMgr::SelectFormContainer](imapiformmgr-selectformcontainer.md)
  
[MAPIOpenLocalFormContainer](mapiopenlocalformcontainer.md)
  
[IMAPIFormMgr : IUnknown](imapiformmgriunknown.md)


[MFCMAPI 代码示例](mfcmapi-as-a-code-sample.md)

