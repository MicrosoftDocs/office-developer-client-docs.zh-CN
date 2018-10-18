---
<span data-ttu-id="1cc50-101"><<<<<<< 标头标题： NumericScale 和 Precision 属性示例 （VC + +） TOCTitle: NumericScale 和 Precision 属性示例 （VC + +） === 标题： NumericScale 和 Precision 属性示例 （VC + +） TOCTitle: NumericScale 和Precision 属性示例 （VC + +）</span><span class="sxs-lookup"><span data-stu-id="1cc50-101"><<<<<<< HEAD title: NumericScale and Precision Properties Example (VC++) TOCTitle: NumericScale and Precision Properties Example (VC++) ======= title: NumericScale and Precision properties example (VC++) TOCTitle: NumericScale and Precision properties example (VC++)</span></span>
>>>>>>> <span data-ttu-id="1cc50-102">母版页 ms:assetid: da4bec90-b039-1764-3b8b-c74bb725da61 ms:mtpsurl: https://msdn.microsoft.com/library/JJ250098(v=office.15) ms:contentKeyID: 48548078 ms.date: 09/18/2015 mtps_version: office.15.aspx</span><span class="sxs-lookup"><span data-stu-id="1cc50-102">master ms:assetid: da4bec90-b039-1764-3b8b-c74bb725da61 ms:mtpsurl: https://msdn.microsoft.com/library/JJ250098(v=office.15) ms:contentKeyID: 48548078 ms.date: 09/18/2015 mtps_version: v=office.15</span></span>
---

<span data-ttu-id="1cc50-103"><<<<<<< 标头</span><span class="sxs-lookup"><span data-stu-id="1cc50-103"><<<<<<< HEAD</span></span>
# <a name="numericscale-and-precision-properties-example-vc"></a><span data-ttu-id="1cc50-104">NumericScale 和 Precision 属性示例 (VC++)</span><span class="sxs-lookup"><span data-stu-id="1cc50-104">NumericScale and Precision Properties Example (VC++)</span></span>
=======
# <a name="numericscale-and-precision-properties-example-vc"></a><span data-ttu-id="1cc50-105">NumericScale 和 Precision 属性示例 （VC + +）</span><span class="sxs-lookup"><span data-stu-id="1cc50-105">NumericScale and Precision properties example (VC++)</span></span>
>>>>>>> <span data-ttu-id="1cc50-106">master</span><span class="sxs-lookup"><span data-stu-id="1cc50-106">master</span></span>


<span data-ttu-id="1cc50-107">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="1cc50-107">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="1cc50-108">本示例演示 [Column](numericscale-property-adox.md) 对象的 [NumericScale](precision-property-adox.md) 和 [Precision](column-object-adox.md) 属性。</span><span class="sxs-lookup"><span data-stu-id="1cc50-108">This example demonstrates the [NumericScale](numericscale-property-adox.md) and [Precision](precision-property-adox.md) properties of the [Column](column-object-adox.md) object.</span></span> <span data-ttu-id="1cc50-109">此代码将显示*Northwind*数据库的**订单明细**表及其值。</span><span class="sxs-lookup"><span data-stu-id="1cc50-109">This code displays their value for the **Order Details** table of the *Northwind* database.</span></span>

```cpp 
 
// BeginNumericScalePrecCpp 
#import "c:\Program Files\Common Files\system\ado\msadox.dll" no_namespace 
#import "c:\Program Files\Common Files\system\ado\msado15.dll" 
 
#include "iostream.h" 
#include "stdio.h" 
#include "conio.h" 
 
//Function declarations 
inline void TESTHR(HRESULT x) {if FAILED(x) _com_issue_error(x);}; 
void NumericScalePrecX(void); 
 
////////////////////////////////////////////////////////// 
// // 
// Main Function // 
// // 
////////////////////////////////////////////////////////// 
void main() 
{ 
 if(FAILED(::CoInitialize(NULL))) 
 return; 
 
 NumericScalePrecX(); 
 
 ::CoUninitialize(); 
} 
 
////////////////////////////////////////////////////////// 
// // 
// NumericScalePrecX Function // 
// // 
////////////////////////////////////////////////////////// 
void NumericScalePrecX(void) 
{ 
 HRESULT hr = S_OK; 
 
 // Define ADOX object pointers. 
 // Initialize pointers on define. 
 // These are in the ADOX:: namespace. 
 _CatalogPtr m_pCatalog = NULL; 
 _TablePtr m_pTable = NULL; 
 _ColumnPtr m_pColumn = NULL; 
 
 //Define ADODB object pointers 
 ADODB::_ConnectionPtr m_pCnn = NULL; 
 
 //Declare string variables 
 _bstr_t strCnn("Provider='Microsoft.JET.OLEDB.4.0';" 
 "Data Source='c:\\Program Files\\Microsoft Office\\" 
 "Office\\Samples\\Northwind.mdb';"); 
 try 
 { 
 TESTHR(hr = m_pCnn.CreateInstance(__uuidof(ADODB::Connection))); 
 
 TESTHR(hr = m_pCatalog.CreateInstance(__uuidof (Catalog))); 
 
 // Connect the catalog. 
 m_pCnn->Open (strCnn, "", "", NULL); 
 
 m_pCatalog->PutActiveConnection(variant_t((IDispatch *)m_pCnn)); 
 
 // Retrieve the Order Details table 
 m_pTable = m_pCatalog->Tables->GetItem("Order Details"); 
 
 // Display numeric scale and precision of 
 // small integer fields. 
 _variant_t vIndex; 
 for (long lIndex=0; lIndex < m_pTable->Columns->Count; lIndex++) 
 { 
 vIndex = lIndex ; 
 m_pColumn = m_pTable->Columns->GetItem(vIndex); 
 if(m_pColumn->Type == adSmallInt) 
 { 
 cout << "Column: " << m_pColumn->GetName() << endl; 
 cout << "Numeric scale: " << (_bstr_t) m_pColumn-> 
 GetNumericScale() << endl; 
 cout << "Precision: " << m_pColumn->GetPrecision() << 
 endl; 
 } 
 } 
 } 
 catch(_com_error &e) 
 { 
 // Notify the user of errors if any. 
 _bstr_t bstrSource(e.Source()); 
 _bstr_t bstrDescription(e.Description()); 
 
 printf("\n\tSource : %s \n\tdescription : %s \n ", 
 (LPCSTR)bstrSource,(LPCSTR)bstrDescription); 
 } 
 catch(...) 
 { 
 cout << "Error occured in NumericScalePrecX...."<< endl; 
 } 
} 
// EndNumericScalePrecCpp 
```

