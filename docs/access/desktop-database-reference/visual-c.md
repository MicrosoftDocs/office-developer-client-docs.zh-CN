---
title: Visual c + + （访问桌面数据库参考 （英文）
TOCTitle: Visual C++
ms:assetid: 31d27968-e7bd-02fa-efad-26039bea30b8
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249091(v=office.15)
ms:contentKeyID: 48544062
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 1a12304cc30e9e653f1cb10343cac390395961fa
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25466446"
---
# <a name="visual-c"></a><span data-ttu-id="bdfe8-102">Visual C++</span><span class="sxs-lookup"><span data-stu-id="bdfe8-102">Visual C++</span></span>


<span data-ttu-id="bdfe8-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="bdfe8-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="bdfe8-p101">这是如何在 Microsoft Visual C++ 中实例化 ADO 事件的架构说明。有关完整说明，请参阅 [ADO 事件模型示例 (VC++)](ado-events-model-example-vc.md)。</span><span class="sxs-lookup"><span data-stu-id="bdfe8-p101">This is a schematic description of how to instantiate ADO events in Microsoft Visual C++. See [ADO Events Model Example (VC++)](ado-events-model-example-vc.md) for a complete description.</span></span>

<span data-ttu-id="bdfe8-106">创建从在文件 adoint.h 中找到的 **ConnectionEventsVt** 和 **RecordsetEventsVt** 接口派生的类。</span><span class="sxs-lookup"><span data-stu-id="bdfe8-106">Create classes derived from the **ConnectionEventsVt** and **RecordsetEventsVt** interfaces found in the file adoint.h.</span></span>

```cpp 
 
// BeginEventExampleVC01 
class CConnEvent : public ConnectionEventsVt 
{ 
 public: 
 STDMETHODIMP InfoMessage( 
 ADOError *pError, 
 EventStatusEnum *adStatus, 
 _ADOConnection *pConnection); 
... 
} 
 
class CRstEvent : public RecordsetEventsVt 
{ 
 public: 
 STDMETHODIMP WillChangeField( 
 LONG cFields, 
 VARIANT Fields, 
 EventStatusEnum *adStatus, 
 _ADORecordset *pRecordset); 
... 
} 
// EndEventExampleVC01 
```

<span data-ttu-id="bdfe8-107">在两个类中都实现了每个事件处理程序方法。</span><span class="sxs-lookup"><span data-stu-id="bdfe8-107">Implement each of the event-handler methods in both classes.</span></span> <span data-ttu-id="bdfe8-108">就足够每种方法只是返回 HRESULT S\_确定。</span><span class="sxs-lookup"><span data-stu-id="bdfe8-108">It is sufficient that each method merely return an HRESULT of S\_OK.</span></span> <span data-ttu-id="bdfe8-109">但是，当您通知事件处理程序可用时，默认情况下它们将被连续调用。</span><span class="sxs-lookup"><span data-stu-id="bdfe8-109">However, when you make it known that your event handlers are available, they will be called continuously by default.</span></span> <span data-ttu-id="bdfe8-110">而您可能希望通过将 **adStatus** 设置为 **adStatusUnwantedEvent** ，以便在第一次通知之后不再请求进一步的通知。</span><span class="sxs-lookup"><span data-stu-id="bdfe8-110">Instead, you might want to request no further notification after the first time by setting **adStatus** to **adStatusUnwantedEvent**.</span></span>

```cpp 
 
// BeginEventExampleVC02 
STDMETHODIMP CConnEvent::ConnectComplete( 
 ADOError *pError, 
 EventStatusEnum *adStatus, 
 _ADOConnection *pConnection) 
 { 
 *adStatus = adStatusUnwantedEvent; 
 return S_OK; 
 } 
 
// EndEventExampleVC02 
```

<span data-ttu-id="bdfe8-p103">事件类继承自 **IUnknown** ，所以还必须实现 **QueryInterface** 、 **AddRef** 和 **Release** 方法。还要实现类构造函数和析构函数。请选择您最熟悉的 Visual C++ 工具来简化这部分任务。</span><span class="sxs-lookup"><span data-stu-id="bdfe8-p103">The event classes inherit from **IUnknown**, so you must also implement the **QueryInterface**, **AddRef**, and **Release** methods. Also implement class constructors and destructors. Choose the Visual C++ tools with which you are most comfortable to simplify this part of the task.</span></span>

<span data-ttu-id="bdfe8-p104">通过发出 **Recordset** 和 [Connection](recordset-object-ado.md) 对象的 [QueryInterface](connection-object-ado.md) 来获取 **IConnectionPointContainer** 和 **IConnectionPoint** 接口，以便通知事件处理程序可用。然后对每个类发出 **IConnectionPoint::Advise** 。</span><span class="sxs-lookup"><span data-stu-id="bdfe8-p104">Make it known that your event handlers are available by issuing **QueryInterface** on the [Recordset](recordset-object-ado.md) and [Connection](connection-object-ado.md) objects for the **IConnectionPointContainer** and **IConnectionPoint** interfaces. Then issue **IConnectionPoint::Advise** for each class.</span></span>

<span data-ttu-id="bdfe8-116">例如，假设您正在使用返回 **True** 的布尔函数，如果它成功，将通知 **Recordset** 对象您的事件处理程序已经可用。</span><span class="sxs-lookup"><span data-stu-id="bdfe8-116">For example, assume you are using a Boolean function that returns **True** if it successfully informs a **Recordset** object that you have event handlers available.</span></span>

```cpp 
 
// BeginEventExampleVC03 
HRESULT hr; 
DWORD dwEvtClass; 
IConnectionPointContainer *pCPC = NULL; 
IConnectionPoint *pCP = NULL; 
CRstEvent *pRStEvent = NULL; 
... 
_RecordsetPtr pRs; 
pRs.CreateInstance(__uuidof(Recordset)); 
pRStEvent = new CRstEvent; 
if (pRStEvent == NULL) return FALSE; 
... 
hr = pRs->QueryInterface(IID_IConnectionPointContainer, (LPVOID *)&pCPC); 
if (FAILED(hr)) return FALSE; 
hr = pCPC->FindConnectionPoint(RecordsetEvents, &pCP); 
pCPC->Release(); // Always Release now, even before checking. 
if (FAILED(hr)) return FALSE; 
hr = pCP->Advise(pRstEvent, &dwEvtClass); //Turn on event support. 
pCP->Release(); 
if (FAILED(hr)) return FALSE; 
... 
return TRUE; 
... 
// EndEventExampleVC03 
```

<span data-ttu-id="bdfe8-117">在这里，将启用 **RecordsetEvent** 系列的事件，在发生 **Recordset** 事件时将调用您的方法。</span><span class="sxs-lookup"><span data-stu-id="bdfe8-117">At this point, events for the **RecordsetEvent** family are enabled and your methods will be called as **Recordset** events occur.</span></span>

<span data-ttu-id="bdfe8-118">随后，如果希望使事件处理程序不可用，请再次获取连接点，并发出 **IConnectionPoint::Unadvise** 方法。</span><span class="sxs-lookup"><span data-stu-id="bdfe8-118">Later, when you want to make your event handlers unavailable, get the connection point again and issue the **IConnectionPoint::Unadvise** method.</span></span>

```cpp 
 
// BeginEventExampleVC04 
... 
hr = pCP->Unadvise(dwEvtClass); //Turn off event support. 
pCP->Release(); 
if (FAILED(hr)) return FALSE; 
... 
// EndEventExampleVC04 
```

<span data-ttu-id="bdfe8-119">必须在合适的时候释放接口并销毁类对象。</span><span class="sxs-lookup"><span data-stu-id="bdfe8-119">You must release interfaces and destroy class objects as appropriate.</span></span>

<span data-ttu-id="bdfe8-120">以下代码显示 **Recordset** 事件接收器类的完整示例。</span><span class="sxs-lookup"><span data-stu-id="bdfe8-120">The following code shows a complete example of a **Recordset** Event sink class.</span></span>

```vb 
 
// BeginEventExampleVC05 
#include <adoint.h> 
 
class CADORecordsetEvents : public RecordsetEventsVt 
{ 
public : 
 
 ULONG m_ulRefCount; 
 CADORecordsetEvents():m_ulRefCount(1){} 
 
 STDMETHOD(QueryInterface)(REFIID iid, LPVOID * ppvObject) 
 { 
 if (IsEqualIID(__uuidof(IUnknown), iid) || 
 IsEqualIID(__uuidof(RecordsetEventsVt), iid)) 
 { 
 *ppvObject = this; 
 return S_OK; 
 } 
 else 
 return E_NOINTERFACE; 
 } 
 
 STDMETHOD_(ULONG, AddRef)() 
 { 
 return m_ulRefCount++; 
 } 
 
 STDMETHOD_(ULONG, Release)() 
 { 
 if (--m_ulRefCount == 0) 
 { 
 delete this; 
 return 0; 
 } 
 else 
 return m_ulRefCount; 
 } 
 
 
 STDMETHOD(WillChangeField)( 
 LONG cFields, 
 VARIANT Fields, 
 EventStatusEnum *adStatus, 
 _ADORecordset *pRecordset) 
 { 
 *adStatus = adStatusUnwantedEvent; 
 return S_OK; 
 } 
 
 STDMETHOD(FieldChangeComplete)( 
 LONG cFields, 
 VARIANT Fields, 
 ADOError *pError, 
 EventStatusEnum *adStatus, 
 _ADORecordset *pRecordset) 
 { 
 *adStatus = adStatusUnwantedEvent; 
 return S_OK; 
 } 
 
 STDMETHOD(WillChangeRecord)( 
 EventReasonEnum adReason, 
 LONG cRecords, 
 EventStatusEnum *adStatus, 
 _ADORecordset *pRecordset) 
 { 
 *adStatus = adStatusUnwantedEvent; 
 return S_OK; 
 } 
 
 STDMETHOD(RecordChangeComplete)( 
 EventReasonEnum adReason, 
 LONG cRecords, 
 ADOError *pError, 
 EventStatusEnum *adStatus, 
 _ADORecordset *pRecordset) 
 { 
 *adStatus = adStatusUnwantedEvent; 
 return S_OK; 
 } 
 
 
 STDMETHOD(WillChangeRecordset)( 
 EventReasonEnum adReason, 
 EventStatusEnum *adStatus, 
 _ADORecordset *pRecordset) 
 { 
 *adStatus = adStatusUnwantedEvent; 
 return S_OK; 
 } 
 
 
 STDMETHOD(RecordsetChangeComplete)( 
 EventReasonEnum adReason, 
 ADOError *pError, 
 EventStatusEnum *adStatus, 
 _ADORecordset *pRecordset) 
 { 
 *adStatus = adStatusUnwantedEvent; 
 return S_OK; 
 } 
 
 
 STDMETHOD(WillMove)( 
 EventReasonEnum adReason, 
 EventStatusEnum *adStatus, 
 _ADORecordset *pRecordset) 
 { 
 *adStatus = adStatusUnwantedEvent; 
 return S_OK; 
 } 
 
 
 STDMETHOD(MoveComplete)( 
 EventReasonEnum adReason, 
 ADOError *pError, 
 EventStatusEnum *adStatus, 
 _ADORecordset *pRecordset) 
 { 
 *adStatus = adStatusUnwantedEvent; 
 return S_OK; 
 } 
 
 STDMETHOD(EndOfRecordset)( 
 VARIANT_BOOL *fMoreData, 
 EventStatusEnum *adStatus, 
 _ADORecordset *pRecordset) 
 { 
 *adStatus = adStatusUnwantedEvent; 
 return S_OK; 
 } 
 
 STDMETHOD(FetchProgress)( 
 long Progress, 
 long MaxProgress, 
 EventStatusEnum *adStatus, 
 _ADORecordset *pRecordset) 
 { 
 *adStatus = adStatusUnwantedEvent; 
 return S_OK; 
 } 
 
 
 STDMETHOD(FetchComplete)( 
 ADOError *pError, 
 EventStatusEnum *adStatus, 
 _ADORecordset *pRecordset) 
 { 
 *adStatus = adStatusUnwantedEvent; 
 return S_OK; 
 } 
 
}; 
// EndEventExampleVC05 
```

