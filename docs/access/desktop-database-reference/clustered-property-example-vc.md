---
<span data-ttu-id="94a5a-101"><<<<<<< 标头标题： 群集属性示例 （VC + +） TOCTitle： 群集属性示例 （VC + +） === 标题： Clustered 的属性示例 （VC + +） TOCTitle: Clustered 的属性示例 （VC + +）</span><span class="sxs-lookup"><span data-stu-id="94a5a-101"><<<<<<< HEAD title: Clustered Property Example (VC++) TOCTitle: Clustered Property Example (VC++) ======= title: Clustered property example (VC++) TOCTitle: Clustered property example (VC++)</span></span>
>>>>>>> <span data-ttu-id="94a5a-102">母版页 ms:assetid: a262e38e-ce44-66cb-1adf-fad8e6b840d1 ms:mtpsurl: https://msdn.microsoft.com/library/JJ249748(v=office.15) ms:contentKeyID: 48546761 ms.date: 09/18/2015 mtps_version: office.15.aspx</span><span class="sxs-lookup"><span data-stu-id="94a5a-102">master ms:assetid: a262e38e-ce44-66cb-1adf-fad8e6b840d1 ms:mtpsurl: https://msdn.microsoft.com/library/JJ249748(v=office.15) ms:contentKeyID: 48546761 ms.date: 09/18/2015 mtps_version: v=office.15</span></span>
---

<span data-ttu-id="94a5a-103"><<<<<<< 标头</span><span class="sxs-lookup"><span data-stu-id="94a5a-103"><<<<<<< HEAD</span></span>
# <a name="clustered-property-example-vc"></a><span data-ttu-id="94a5a-104">Clustered 属性示例 (VC++)</span><span class="sxs-lookup"><span data-stu-id="94a5a-104">Clustered Property Example (VC++)</span></span>
=======
# <a name="clustered-property-example-vc"></a><span data-ttu-id="94a5a-105">Clustered 的属性示例 （VC + +）</span><span class="sxs-lookup"><span data-stu-id="94a5a-105">Clustered property example (VC++)</span></span>
>>>>>>> <span data-ttu-id="94a5a-106">master</span><span class="sxs-lookup"><span data-stu-id="94a5a-106">master</span></span>


<span data-ttu-id="94a5a-107">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="94a5a-107">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="94a5a-108">本示例演示 [Index](clustered-property-adox.md) 的 [Clustered](index-object-adox.md) 属性。</span><span class="sxs-lookup"><span data-stu-id="94a5a-108">This example demonstrates the [Clustered](clustered-property-adox.md) property of an [Index](index-object-adox.md).</span></span> <span data-ttu-id="94a5a-109">请注意，Microsoft Jet 数据库不支持聚簇的索引，因此本示例将返回**False**的**Clustered**属性的*Northwind*数据库中的所有索引。</span><span class="sxs-lookup"><span data-stu-id="94a5a-109">Note that Microsoft Jet databases do not support clustered indexes, so this example will return **False** for the **Clustered** property of all indexes in the *Northwind* database.</span></span>

```cpp 
 
// BeginClusteredCpp 
#import "c:\Program Files\Common Files\system\ado\msadox.dll" no_namespace 
 
#include "iostream.h" 
#include "stdio.h" 
#include "conio.h" 
 
//Function declarations 
inline void TESTHR(HRESULT x) {if FAILED(x) _com_issue_error(x);}; 
void ClusteredX(void); 
 
////////////////////////////////////////////////////////// 
// // 
// Main Function // 
// // 
////////////////////////////////////////////////////////// 
void main() 
{ 
 if(FAILED(::CoInitialize(NULL))) 
 return; 
 
 ClusteredX(); 
 
 ::CoUninitialize(); 
} 
 
////////////////////////////////////////////////////////// 
// // 
// ClusteredX Function // 
// // 
////////////////////////////////////////////////////////// 
void ClusteredX() 
{ 
 HRESULT hr = S_OK; 
 
 // Define ADOX object pointers. 
 // Initialize pointers on define. 
 // These are in the ADOX:: namespace. 
 _CatalogPtr m_pCatalog = NULL; 
 _TablePtr m_pTable = NULL; 
 _IndexPtr m_pIndex = NULL; 
 
 //Define other variables here 
 _variant_t vIndex; 
 try 
 { 
 TESTHR(hr = m_pCatalog.CreateInstance(__uuidof(Catalog))); 
 
 // Connect to the catalog. 
 m_pCatalog->PutActiveConnection( 
 "Provider='Microsoft.JET.OLEDB.4.0';data source=" 
 "'c:\\Program Files\\Microsoft Office\\Office\\Samples" 
 "\\Northwind.mdb';"); 
 
 int iLineCnt = 1; 
 //Enumerate Tables. 
 for(short iTable = 0;iTable < m_pCatalog->Tables->Count;iTable++) 
 { 
 vIndex = iTable; 
 m_pTable = m_pCatalog->Tables->GetItem(vIndex); 
 
 //Enumerate Indexes. 
 for(short iIndex = 0;iIndex < m_pTable->Indexes->Count; 
 iIndex++) 
 { 
 vIndex = iIndex; 
 m_pIndex = m_pTable->Indexes->GetItem(vIndex); 
 cout << m_pTable->Name << " " ; 
 cout << m_pIndex->Name << " " << (m_pIndex-> 
 GetClustered() ? "True" : "False") << endl; 
 
 if (iLineCnt%15 == 0) 
 { 
 printf("\nPress any key to continue...\n"); 
 getch(); 
 } 
 iLineCnt++; 
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
 cout << "Error occured in ClusteredX...."<< endl; 
 } 
} 
// EndClusteredCpp 
```

