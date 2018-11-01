---
title: 说明，HelpContext HelpFile 属性示例 （VJ + +）
TOCTitle: Description, HelpContext, HelpFile, NativeError, Number, Source, and SQLState properties example (VJ++)
ms:assetid: daa3ff89-9f7f-f832-479e-bbb51c918ae8
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250100(v=office.15)
ms:contentKeyID: 48548085
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 75ba9554b4c4d6e2da82a0fe13437a3bebea3d07
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25880913"
---
# <a name="description-helpcontext-helpfile-nativeerror-number-source-and-sqlstate-properties-example-vj"></a><span data-ttu-id="ad926-102">Description、HelpContext、HelpFile、NativeError、Number、Source 和 SQLState 属性示例 (VJ++)</span><span class="sxs-lookup"><span data-stu-id="ad926-102">Description, HelpContext, HelpFile, NativeError, Number, Source, and SQLState properties example (VJ++)</span></span>


<span data-ttu-id="ad926-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="ad926-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="ad926-104">此示例触发一个错误，将其捕获，并显示产生的 [Error](description-property-ado.md) 对象的 [Description](helpcontext-helpfile-properties-ado.md)、[HelpContext](helpcontext-helpfile-properties-ado.md)、[HelpFile](nativeerror-property-ado.md)、[NativeError](number-property-ado.md)、[Number](source-property-ado-error.md)、[Source](sqlstate-property-ado.md) 和 [SQLState](error-object-ado.md) 属性。</span><span class="sxs-lookup"><span data-stu-id="ad926-104">This example triggers an error, traps it, and displays the [Description](description-property-ado.md), [HelpContext](helpcontext-helpfile-properties-ado.md), [HelpFile](helpcontext-helpfile-properties-ado.md), [NativeError](nativeerror-property-ado.md), [Number](number-property-ado.md), [Source](source-property-ado-error.md), and [SQLState](sqlstate-property-ado.md) properties of the resulting [Error](error-object-ado.md) object.</span></span>

```java
    // BeginDescriptionJ
    // The WFC class includes the ADO objects.
    
    import com.ms.wfc.data.*;
    import java.io.* ;
    
    public class DescriptionX
    {
       // The main entry point for the application.
    
       public static void main (String[] args)
       {
          DescriptionX();
          System.exit(0);
       }
    
       // DescriptionX function
    
       static void DescriptionX()
       {
          // Declarations.
          BufferedReader in = new 
             BufferedReader(new InputStreamReader(System.in));
    
          // Define ADO Objects.
          Connection cnConn1 = null;
    
          try
          {
             // Intentionally trigger an error.
             cnConn1 = new Connection();
             cnConn1.open("nothing");
          }
          catch( AdoException ae )
          {
             // Notify user of any errors that result from ADO.
             PrintProviderError(cnConn1);
          }
    
          try
          {
             System.out.println("\nPress <Enter> key to continue.");
             in.readLine();
          }
          // System read requires this catch.
          catch( java.io.IOException je)
          {
             PrintIOError(je);
          }
      
       }
    
       // PrintProviderError Function
    
       static void PrintProviderError( Connection Cnn1 )
       {
          // Print Provider errors from Connection object.
          // ErrItem is an item object in the Connections Errors collection.
          com.ms.wfc.data.Error  ErrItem = null;
          long nCount = 0;
          int  i      = 0;
    
          nCount = Cnn1.getErrors().getCount();
    
          // If there are any errors in the collection, print them.
          if( nCount > 0);
          {
             // Collection ranges from 0 to nCount - 1
             for (i = 0; i< nCount; i++)
             {
                ErrItem = Cnn1.getErrors().getItem(i);
                System.out.println("\t Error number: " + ErrItem.getNumber()
                   + "\t" + ErrItem.getDescription() );
             }
          }
    
       }
    
       // PrintIOError Function
    
       static void PrintIOError( java.io.IOException je)
       {
          System.out.println("Error \n");
          System.out.println("\tSource = " + je.getClass() + "\n");
          System.out.println("\tDescription = " + je.getMessage() + "\n");
       }
    }
    // EndDescriptionJ
```
