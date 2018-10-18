---
<span data-ttu-id="6df36-101"><<<<<<< 标头标题： 说明，HelpContext HelpFile 属性示例 （VC + +） TOCTitle: Description、 HelpContext、 HelpFile、 NativeError、 号码、 源和 SQLState 属性示例 （VC + +） === 标题: 说明，HelpFile 属性示例 （VC + +） HelpContext TOCTitle: Description、 HelpContext、 HelpFile、 NativeError、 号码、 源和 SQLState 属性示例 （VC + +）</span><span class="sxs-lookup"><span data-stu-id="6df36-101"><<<<<<< HEAD title: Description, HelpContext, HelpFile Properties Example (VC++) TOCTitle: Description, HelpContext, HelpFile, NativeError, Number, Source, and SQLState Properties Example (VC++) ======= title: Description, HelpContext, HelpFile properties example (VC++) TOCTitle: Description, HelpContext, HelpFile, NativeError, Number, Source, and SQLState properties example (VC++)</span></span>
>>>>>>> <span data-ttu-id="6df36-102">母版页 ms:assetid: 1375a0e6-c61b-aba5-4d7c-5db597ef873e ms:mtpsurl: https://msdn.microsoft.com/library/JJ248908(v=office.15) ms:contentKeyID: 48543369 ms.date: 09/18/2015 mtps_version: office.15.aspx</span><span class="sxs-lookup"><span data-stu-id="6df36-102">master ms:assetid: 1375a0e6-c61b-aba5-4d7c-5db597ef873e ms:mtpsurl: https://msdn.microsoft.com/library/JJ248908(v=office.15) ms:contentKeyID: 48543369 ms.date: 09/18/2015 mtps_version: v=office.15</span></span>
---

<span data-ttu-id="6df36-103"><<<<<<< 标头</span><span class="sxs-lookup"><span data-stu-id="6df36-103"><<<<<<< HEAD</span></span>
# <a name="description-helpcontext-helpfile-nativeerror-number-source-and-sqlstate-properties-example-vc"></a><span data-ttu-id="6df36-104">Description、HelpContext、HelpFile、NativeError、Number、Source 和 SQLState 属性示例 (VC++)</span><span class="sxs-lookup"><span data-stu-id="6df36-104">Description, HelpContext, HelpFile, NativeError, Number, Source, and SQLState Properties Example (VC++)</span></span>
=======
# <a name="description-helpcontext-helpfile-nativeerror-number-source-and-sqlstate-properties-example-vc"></a><span data-ttu-id="6df36-105">Description、 HelpContext、 HelpFile、 NativeError、 号码、 源和 SQLState 属性示例 （VC + +）</span><span class="sxs-lookup"><span data-stu-id="6df36-105">Description, HelpContext, HelpFile, NativeError, Number, Source, and SQLState properties example (VC++)</span></span>
>>>>>>> <span data-ttu-id="6df36-106">master</span><span class="sxs-lookup"><span data-stu-id="6df36-106">master</span></span>


<span data-ttu-id="6df36-107">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="6df36-107">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="6df36-108">此示例触发一个错误，将其捕获，并显示产生的 [Error](description-property-ado.md) 对象的 [Description](helpcontext-helpfile-properties-ado.md)、[HelpContext](helpcontext-helpfile-properties-ado.md)、[HelpFile](nativeerror-property-ado.md)、[NativeError](number-property-ado.md)、[Number](source-property-ado-error.md)、[Source](sqlstate-property-ado.md) 和 [SQLState](error-object-ado.md) 属性。</span><span class="sxs-lookup"><span data-stu-id="6df36-108">This example triggers an error, traps it, and displays the [Description](description-property-ado.md), [HelpContext](helpcontext-helpfile-properties-ado.md), [HelpFile](helpcontext-helpfile-properties-ado.md), [NativeError](nativeerror-property-ado.md), [Number](number-property-ado.md), [Source](source-property-ado-error.md), and [SQLState](sqlstate-property-ado.md) properties of the resulting [Error](error-object-ado.md) object.</span></span>

```cpp
    // BeginDescriptionCpp
    #import "C:\Program Files\Common Files\System\ADO\msado15.dll"     no_namespace rename("EOF", "EndOfFile")
    
    #include <ole2.h>
    #include <stdio.h>
    #include<conio.h>
    
    // Function declarations
    inline void TESTHR(HRESULT x) {if FAILED(x) _com_issue_error(x);};
    void DescriptionX(void);
    void PrintProviderError(_ConnectionPtr pConnection);
    void PrintComError(_com_error &e);
    
    ///////////////////////////////////////////////////////////
    //                                                       //
    //      Main Function                                    //
    //                                                       //
    ///////////////////////////////////////////////////////////
    
    void main()
    {
        if(FAILED(::CoInitialize(NULL)))
            return;
    
        DescriptionX();
    
        //Wait here for user to see the output..
        printf("\nPress any key to continue...");
        getch();
        ::CoUninitialize();
    }
    
    ///////////////////////////////////////////////////////////
    //                                                       //
    //      DescriptionX Function                            //
    //                                                       //
    ///////////////////////////////////////////////////////////
    
    void DescriptionX()
    {
        // Define ADO object pointers.
        // Initialize pointers on define.
        // These are in the ADODB::  namespace
        _ConnectionPtr pConnection = NULL;
        ErrorPtr errorLoop = NULL;
    
        //Define Other Variables
        HRESULT hr = S_OK;
        
    
        try
        {
            // Intentionally trigger an error.
            // open connection
            TESTHR(pConnection.CreateInstance(__uuidof(Connection)));
    
            if (FAILED(hr = pConnection->Open("nothing","","",adConnectUnspecified)))
            {
                _com_issue_error(hr);
                exit(1);
            }
    
            // Cleanup object before exit.
            pConnection->Close();
        }
        catch(_com_error)
        {
            // Pass a connection pointer.
            PrintProviderError(pConnection);
        }
    }
    
    ///////////////////////////////////////////////////////////
    //                                                       //
    //      PrintProviderError Function                      //
    //                                                       //
    ///////////////////////////////////////////////////////////
    
    void PrintProviderError(_ConnectionPtr pConnection)
    {
        //Define Other Variables
        HRESULT  hr = S_OK;
        _bstr_t  strError;
        ErrorPtr  pErr = NULL;
    
        try
        {
            // Enumerate Errors collection and display
            // properties of each Error object.
            long nCount = pConnection->Errors->Count;
    
            // Collection ranges from 0 to nCount - 1.
            for(long i = 0; i < nCount; i++)
            {
                pErr = pConnection->Errors->GetItem(i);
                printf("Error #%d\n", pErr->Number);
                printf(" %s\n",(LPCSTR)pErr->Description);
                printf(" (Source: %s)\n",(LPCSTR)pErr->Source);
                printf(" (SQL State: %s)\n",(LPCSTR)pErr->SQLState);
                printf(" (NativeError: %d)\n",(LPCSTR)pErr->NativeError);
                if ((LPCSTR)pErr->GetHelpFile() == NULL)
                {
                    printf("\tNo Help file available\n");
                }
                else
                {
                    printf("\t(HelpFile: %s\n)" ,pErr->HelpFile);
                    printf("\t(HelpContext: %s\n)" , pErr->HelpContext);
                }
            }
        }
        catch(_com_error &e)
        {
            // Notify the user of errors if any.
            PrintComError(e);
        }
    }
    
    ///////////////////////////////////////////////////////////
    //                                                       //
    //      PrintComError Function                           //
    //                                                       //
    ///////////////////////////////////////////////////////////
    
    void PrintComError(_com_error &e)
    {
       // Notify the user of errors if any.
       _bstr_t bstrSource(e.Source());
       _bstr_t bstrDescription(e.Description());
        
        // Print Com errors.
        
       printf("Error\n");
       printf("\tCode = %08lx\n", e.Error());
       printf("\tCode meaning = %s", e.ErrorMessage());
       printf("\tSource = %s\n", (LPCSTR) bstrSource);
       printf("\tDescription = %s\n", (LPCSTR) bstrDescription);
    }
    // EndDescriptionCpp
```
