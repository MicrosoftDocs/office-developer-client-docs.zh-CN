---
title: ADO 事件模型示例 (VC + +)
TOCTitle: ADO Events Model example (VC++)
ms:assetid: 3785406b-844c-419f-e6ac-78aa8c4e78b2
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249132(v=office.15)
ms:contentKeyID: 48544197
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 8e47e8961436be44a78596498754e01e3b0677d1
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32283350"
---
# <a name="ado-events-model-example-vc"></a>ADO 事件模型示例 (VC + +)

**适用于**：Access 2013、Office 2013

[ADO 事件实例化（按语言）](https://docs.microsoft.com/office/client-developer/access/desktop-database-reference/ado-event-instantiation-by-language-ado)的 Visual C++ 部分提供了如何实例化 ADO 事件模型的一般说明。 下面是在由** \#import**指令创建的环境中实例化事件模型的具体示例。

该一般说明使用 **adoint.h** 作为方法签名的参考。 但是, 由于使用了** \#import**指令, 一般说明中的一些详细信息会略微变化:

- 导入指令可将**typedef**以及方法签名数据类型和修饰符解析为其基本窗体。 ** \#**

- 必须覆盖的纯虚方法均以 "**raw\_**" 为前缀。

某些代码仅反映编码样式。

- 指向由 **Advise** 方法使用的 **IUnknown** 的指针是使用对 **QueryInterface** 的调用显式获取的。

- 不需要在类定义中对析构函数进行显式编码。

- 您可能需要对 QueryInterface、AddRef 和 Release 的更强大的实现进行编码。

- uuidof () 指令被广泛用于获取接口 id。 ** \_ \_**

最后，本示例包含了一些工作代码。

- 本示例是作为控制台应用程序进行编写的。

- 您应该在注释 "//执行一些工作" 下插入自己的代码。

- 所有事件处理程序默认情况下不执行任何操作，且取消进一步的通知。您应该插入您的应用程序的适当代码，并在需要的情况下允许通知。

<!-- end list -->

```cpp 
 
// eventmodel.cpp : Defines the entry point for the console application. 
// 
 
#import "c:\Program Files\Common Files\System\ADO\msado15.dll" no_namespace rename("EOF", "EndOfFile") 
#include <comdef.h> 
#include <stdio.h> 
 
//----The Connection events---------------------------------------------- 
 
class CConnEvent : public ConnectionEventsVt 
{ 
private: 
 ULONG m_cRef; 
 public: 
 CConnEvent() { m_cRef = 0; }; 
 ~CConnEvent() {}; 
 
 
 STDMETHODIMP QueryInterface(REFIID riid, void ** ppv); 
 STDMETHODIMP_(ULONG) AddRef(void); 
 STDMETHODIMP_(ULONG) Release(void); 
 
 STDMETHODIMP raw_InfoMessage( 
 struct Error *pError, 
 EventStatusEnum *adStatus, 
 struct _Connection *pConnection); 
 
 STDMETHODIMP raw_BeginTransComplete( 
 LONG TransactionLevel, 
 struct Error *pError, 
 EventStatusEnum *adStatus, 
 struct _Connection *pConnection); 
 
 STDMETHODIMP raw_CommitTransComplete( 
 struct Error *pError, 
 EventStatusEnum *adStatus, 
 struct _Connection *pConnection); 
 
 STDMETHODIMP raw_RollbackTransComplete( 
 struct Error *pError, 
 EventStatusEnum *adStatus, 
 struct _Connection *pConnection); 
 
 STDMETHODIMP raw_WillExecute( 
 BSTR *Source, 
 CursorTypeEnum *CursorType, 
 LockTypeEnum *LockType, 
 long *Options, 
 EventStatusEnum *adStatus, 
 struct _Command *pCommand, 
 struct _Recordset *pRecordset, 
 struct _Connection *pConnection); 
 
 STDMETHODIMP raw_ExecuteComplete( 
 LONG RecordsAffected, 
 struct Error *pError, 
 EventStatusEnum *adStatus, 
 struct _Command *pCommand, 
 struct _Recordset *pRecordset, 
 struct _Connection *pConnection); 
 
 STDMETHODIMP raw_WillConnect( 
 BSTR *ConnectionString, 
 BSTR *UserID, 
 BSTR *Password, 
 long *Options, 
 EventStatusEnum *adStatus, 
 struct _Connection *pConnection); 
 
 STDMETHODIMP raw_ConnectComplete( 
 struct Error *pError, 
 EventStatusEnum *adStatus, 
 struct _Connection *pConnection); 
 
 STDMETHODIMP raw_Disconnect( 
 EventStatusEnum *adStatus, 
 struct _Connection *pConnection); 
}; 
 
//-----The Recordset events---------------------------------------------- 
 
class CRstEvent : public RecordsetEventsVt 
 { 
 private: 
 ULONG m_cRef; 
 public: 
 CRstEvent() { m_cRef = 0; }; 
 ~CRstEvent() {}; 
 
 STDMETHODIMP QueryInterface(REFIID riid, void ** ppv); 
 STDMETHODIMP_(ULONG) AddRef(void); 
 STDMETHODIMP_(ULONG) Release(void); 
 
 STDMETHODIMP raw_WillChangeField( 
 LONG cFields, 
 VARIANT Fields, 
 EventStatusEnum *adStatus, 
 struct _Recordset *pRecordset); 
 
 STDMETHODIMP raw_FieldChangeComplete( 
 LONG cFields, 
 VARIANT Fields, 
 struct Error *pError, 
 EventStatusEnum *adStatus, 
 struct _Recordset *pRecordset); 
 
 STDMETHODIMP raw_WillChangeRecord( 
 EventReasonEnum adReason, 
 LONG cRecords, 
 EventStatusEnum *adStatus, 
 struct _Recordset *pRecordset); 
 
 STDMETHODIMP raw_RecordChangeComplete( 
 EventReasonEnum adReason, 
 LONG cRecords, 
 struct Error *pError, 
 EventStatusEnum *adStatus, 
 struct _Recordset *pRecordset); 
 
 STDMETHODIMP raw_WillChangeRecordset( 
 EventReasonEnum adReason, 
 EventStatusEnum *adStatus, 
 struct _Recordset *pRecordset); 
 
 STDMETHODIMP raw_RecordsetChangeComplete( 
 EventReasonEnum adReason, 
 struct Error *pError, 
 EventStatusEnum *adStatus, 
 struct _Recordset *pRecordset); 
 
 STDMETHODIMP raw_WillMove( 
 EventReasonEnum adReason, 
 EventStatusEnum *adStatus, 
 struct _Recordset *pRecordset); 
 
 STDMETHODIMP raw_MoveComplete( 
 EventReasonEnum adReason, 
 struct Error *pError, 
 EventStatusEnum *adStatus, 
 struct _Recordset *pRecordset); 
 
 STDMETHODIMP raw_EndOfRecordset( 
 VARIANT_BOOL *fMoreData, 
 EventStatusEnum *adStatus, 
 struct _Recordset *pRecordset); 
 
 STDMETHODIMP raw_FetchProgress( 
 long Progress, 
 long MaxProgress, 
 EventStatusEnum *adStatus, 
 struct _Recordset *pRecordset); 
 
 STDMETHODIMP raw_FetchComplete( 
 struct Error *pError, 
 EventStatusEnum *adStatus, 
 struct _Recordset *pRecordset); 
}; 
 
 
//-----Implement each connection method---------------------------------- 
 
 STDMETHODIMP CConnEvent::raw_InfoMessage( 
 struct Error *pError, 
 EventStatusEnum *adStatus, 
 struct _Connection *pConnection) 
 { 
 *adStatus = adStatusUnwantedEvent; 
 return S_OK; 
 }; 
 
 STDMETHODIMP CConnEvent::raw_BeginTransComplete( 
 LONG TransactionLevel, 
 struct Error *pError, 
 EventStatusEnum *adStatus, 
 struct _Connection *pConnection) 
 { 
 *adStatus = adStatusUnwantedEvent; 
 return S_OK; 
 }; 
 
 STDMETHODIMP CConnEvent::raw_CommitTransComplete( 
 struct Error *pError, 
 EventStatusEnum *adStatus, 
 struct _Connection *pConnection) 
 { 
 *adStatus = adStatusUnwantedEvent; 
 return S_OK; 
 }; 
 
 STDMETHODIMP CConnEvent::raw_RollbackTransComplete( 
 struct Error *pError, 
 EventStatusEnum *adStatus, 
 struct _Connection *pConnection) 
 { 
 *adStatus = adStatusUnwantedEvent; 
 return S_OK; 
 }; 
 
 STDMETHODIMP CConnEvent::raw_WillExecute( 
 BSTR *Source, 
 CursorTypeEnum *CursorType, 
 LockTypeEnum *LockType, 
 long *Options, 
 EventStatusEnum *adStatus, 
 struct _Command *pCommand, 
 struct _Recordset *pRecordset, 
 struct _Connection *pConnection) 
 { 
 *adStatus = adStatusUnwantedEvent; 
 return S_OK; 
 }; 
 
 STDMETHODIMP CConnEvent::raw_ExecuteComplete( 
 LONG RecordsAffected, 
 struct Error *pError, 
 EventStatusEnum *adStatus, 
 struct _Command *pCommand, 
 struct _Recordset *pRecordset, 
 struct _Connection *pConnection) 
 { 
 *adStatus = adStatusUnwantedEvent; 
 return S_OK; 
 }; 
 
 STDMETHODIMP CConnEvent::raw_WillConnect( 
 BSTR *ConnectionString, 
 BSTR *UserID, 
 BSTR *Password, 
 long *Options, 
 EventStatusEnum *adStatus, 
 struct _Connection *pConnection) 
 { 
 *adStatus = adStatusUnwantedEvent; 
 return S_OK; 
 }; 
 
 STDMETHODIMP CConnEvent::raw_ConnectComplete( 
 struct Error *pError, 
 EventStatusEnum *adStatus, 
 struct _Connection *pConnection) 
 { 
 *adStatus = adStatusUnwantedEvent; 
 return S_OK; 
 }; 
 
 STDMETHODIMP CConnEvent::raw_Disconnect( 
 EventStatusEnum *adStatus, 
 struct _Connection *pConnection) 
 { 
 *adStatus = adStatusUnwantedEvent; 
 return S_OK; 
 }; 
 
 
//-----Implement each recordset method----------------------------------- 
 
 STDMETHODIMP CRstEvent::raw_WillChangeField( 
 LONG cFields, 
 VARIANT Fields, 
 EventStatusEnum *adStatus, 
 struct _Recordset *pRecordset) 
 { 
 *adStatus = adStatusUnwantedEvent; 
 return S_OK; 
 }; 
 
 STDMETHODIMP CRstEvent::raw_FieldChangeComplete( 
 LONG cFields, 
 VARIANT Fields, 
 struct Error *pError, 
 EventStatusEnum *adStatus, 
 struct _Recordset *pRecordset) 
 { 
 *adStatus = adStatusUnwantedEvent; 
 return S_OK; 
 }; 
 
 STDMETHODIMP CRstEvent::raw_WillChangeRecord( 
 EventReasonEnum adReason, 
 LONG cRecords, 
 EventStatusEnum *adStatus, 
 struct _Recordset *pRecordset) 
 { 
 *adStatus = adStatusUnwantedEvent; 
 return S_OK; 
 }; 
 
 STDMETHODIMP CRstEvent::raw_RecordChangeComplete( 
 EventReasonEnum adReason, 
 LONG cRecords, 
 struct Error *pError, 
 EventStatusEnum *adStatus, 
 struct _Recordset *pRecordset) 
 { 
 *adStatus = adStatusUnwantedEvent; 
 return S_OK; 
 }; 
 
 STDMETHODIMP CRstEvent::raw_WillChangeRecordset( 
 EventReasonEnum adReason, 
 EventStatusEnum *adStatus, 
 struct _Recordset *pRecordset) 
 { 
 *adStatus = adStatusUnwantedEvent; 
 return S_OK; 
 }; 
 
 STDMETHODIMP CRstEvent::raw_RecordsetChangeComplete( 
 EventReasonEnum adReason, 
 struct Error *pError, 
 EventStatusEnum *adStatus, 
 struct _Recordset *pRecordset) 
 { 
 *adStatus = adStatusUnwantedEvent; 
 return S_OK; 
 }; 
 
 STDMETHODIMP CRstEvent::raw_WillMove( 
 EventReasonEnum adReason, 
 EventStatusEnum *adStatus, 
 struct _Recordset *pRecordset) 
 { 
 *adStatus = adStatusUnwantedEvent; 
 return S_OK; 
 }; 
 
 STDMETHODIMP CRstEvent::raw_MoveComplete( 
 EventReasonEnum adReason, 
 struct Error *pError, 
 EventStatusEnum *adStatus, 
 struct _Recordset *pRecordset) 
 { 
 *adStatus = adStatusUnwantedEvent; 
 return S_OK; 
 }; 
 
 STDMETHODIMP CRstEvent::raw_EndOfRecordset( 
 VARIANT_BOOL *fMoreData, 
 EventStatusEnum *adStatus, 
 struct _Recordset *pRecordset) 
 { 
 *adStatus = adStatusUnwantedEvent; 
 return S_OK; 
 }; 
 
 STDMETHODIMP CRstEvent::raw_FetchProgress( 
 long Progress, 
 long MaxProgress, 
 EventStatusEnum *adStatus, 
 struct _Recordset *pRecordset) 
 { 
 *adStatus = adStatusUnwantedEvent; 
 return S_OK; 
 }; 
 
 STDMETHODIMP CRstEvent::raw_FetchComplete( 
 struct Error *pError, 
 EventStatusEnum *adStatus, 
 struct _Recordset *pRecordset) 
 { 
 *adStatus = adStatusUnwantedEvent; 
 return S_OK; 
 }; 
 
 
//-----Implement QueryInterface, AddRef, and Release--------------------- 
 
 STDMETHODIMP CRstEvent::QueryInterface(REFIID riid, void ** ppv) 
 { 
 *ppv = NULL; 
 if (riid == __uuidof(IUnknown) || 
 riid == __uuidof(RecordsetEventsVt)) *ppv = this; 
 if (*ppv == NULL) 
 return ResultFromScode(E_NOINTERFACE); 
 AddRef(); 
 return NOERROR; 
 } 
 STDMETHODIMP_(ULONG) CRstEvent::AddRef(void) { return ++m_cRef; }; 
 STDMETHODIMP_(ULONG) CRstEvent::Release() 
 { 
 if (0 != --m_cRef) return m_cRef; 
 delete this; 
 return 0; 
 } 
 
 STDMETHODIMP CConnEvent::QueryInterface(REFIID riid, void ** ppv) 
 
 { 
 *ppv = NULL; 
 if (riid == __uuidof(IUnknown) || 
 riid == __uuidof(ConnectionEventsVt)) *ppv = this; 
 if (*ppv == NULL) 
 return ResultFromScode(E_NOINTERFACE); 
 AddRef(); 
 return NOERROR; 
 } 
 STDMETHODIMP_(ULONG) CConnEvent::AddRef() { return ++m_cRef; }; 
 STDMETHODIMP_(ULONG) CConnEvent::Release() 
 { 
 if (0 != --m_cRef) return m_cRef; 
 delete this; 
 return 0; 
 } 
 
//-----Write your main block of code------------------------------------- 
 
int main(int argc, char* argv[]) 
{ 
 HRESULT hr; 
 DWORD dwConnEvt; 
 DWORD dwRstEvt; 
 IConnectionPointContainer *pCPC = NULL; 
 IConnectionPoint *pCP = NULL; 
 IUnknown *pUnk = NULL; 
 CRstEvent *pRstEvent = NULL; 
 CConnEvent *pConnEvent= NULL; 
 int rc = 0; 
 _RecordsetPtr pRst; 
 _ConnectionPtr pConn; 
 
 ::CoInitialize(NULL); 
 
 hr = pConn.CreateInstance(__uuidof(Connection)); 
 if (FAILED(hr)) return rc; 
 
 hr = pRst.CreateInstance(__uuidof(Recordset)); 
 if (FAILED(hr)) return rc; 
 
 // Start using the Connection events 
 
 hr = pConn->QueryInterface(__uuidof(IConnectionPointContainer), 
 (void **)&pCPC); 
 if (FAILED(hr)) return rc; 
 hr = pCPC->FindConnectionPoint(__uuidof(ConnectionEvents), &pCP); 
 pCPC->Release(); 
 if (FAILED(hr)) return rc; 
 
 pConnEvent = new CConnEvent(); 
 hr = pConnEvent->QueryInterface(__uuidof(IUnknown), (void **) &pUnk); 
 if (FAILED(hr)) return rc; 
 hr = pCP->Advise(pUnk, &dwConnEvt); 
 pCP->Release(); 
 if (FAILED(hr)) return rc; 
 
 // Start using the Recordset events 
 
 hr = pRst->QueryInterface(__uuidof(IConnectionPointContainer), 
 (void **)&pCPC); 
 if (FAILED(hr)) return rc; 
 hr = pCPC->FindConnectionPoint(__uuidof(RecordsetEvents), &pCP); 
 pCPC->Release(); 
 if (FAILED(hr)) return rc; 
 
 pRstEvent = new CRstEvent(); 
 hr = pRstEvent->QueryInterface(__uuidof(IUnknown), (void **) &pUnk); 
 if (FAILED(hr)) return rc; 
 hr = pCP->Advise(pUnk, &dwRstEvt); 
 pCP->Release(); 
 if (FAILED(hr)) return rc; 
 
 // Do some work 
 
 pConn->Open("dsn=Pubs;", "MyUserName", "MyPassword", adConnectUnspecified); 
 pRst->Open("SELECT * FROM authors", (IDispatch *) pConn, 
 adOpenStatic, adLockReadOnly, adCmdText); 
 pRst->MoveFirst(); 
 while (pRst->EndOfFile == FALSE) 
 { 
 wprintf(L"Name = '%s'\n", (wchar_t*) 
 ((_bstr_t) pRst->Fields->GetItem("au_lname")->Value)); 
 pRst->MoveNext(); 
 } 
 
 pRst->Close(); 
 pConn->Close(); 
 
 // Stop using the Connection events 
 
 hr = pConn->QueryInterface(__uuidof(IConnectionPointContainer), 
 (void **) &pCPC); 
 if (FAILED(hr)) return rc; 
 hr = pCPC->FindConnectionPoint(__uuidof(ConnectionEvents), &pCP); 
 pCPC->Release(); 
 if (FAILED(hr)) return rc; 
 hr = pCP->Unadvise( dwConnEvt ); 
 pCP->Release(); 
 if (FAILED(hr)) return rc; 
 
 // Stop using the Recordset events 
 hr = pRst->QueryInterface(__uuidof(IConnectionPointContainer), 
 (void **) &pCPC); 
 if (FAILED(hr)) return rc; 
 hr = pCPC->FindConnectionPoint(__uuidof(RecordsetEvents), &pCP); 
 pCPC->Release(); 
 if (FAILED(hr)) return rc; 
 hr = pCP->Unadvise( dwRstEvt ); 
 pCP->Release(); 
 if (FAILED(hr)) return rc; 
 
 CoUninitialize(); 
 return 1; 
} 
```

