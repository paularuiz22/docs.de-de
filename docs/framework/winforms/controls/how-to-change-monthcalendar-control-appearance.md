---
title: 'Vorgehensweise: Ändern der Darstellung des MonthCalendar-Steuerelements in Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- examples [Windows Forms], calendar controls
- MonthCalendar control [Windows Forms], formatting display
ms.assetid: d09b95c9-e108-4608-9b31-b9100c0677bf
ms.openlocfilehash: 233143099996759cc006b3f28b984938554a0d18
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59199920"
---
# <a name="how-to-change-the-windows-forms-monthcalendar-controls-appearance"></a>Vorgehensweise: Ändern der Darstellung des MonthCalendar-Steuerelements in Windows Forms
Die Windows-Formulare <xref:System.Windows.Forms.MonthCalendar> Steuerelement ermöglicht es Ihnen, zum Anpassen der Darstellung des Kalenders in vielerlei Hinsicht. Sie können z. B. das Farbschema festlegen und anzeigen oder ausblenden Wochennummern und dem aktuellen Datum.  
  
### <a name="to-change-the-month-calendars-color-scheme"></a>Der im Monatskalender Farbschema ändern  
  
-   Legen Sie Eigenschaften wie z. B. <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A>, <xref:System.Windows.Forms.MonthCalendar.TitleForeColor%2A> und <xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A>. Die <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A> -Eigenschaft bestimmt auch die Schriftfarbe für die Tage der Woche. Die <xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A> -Eigenschaft bestimmt die Farbe der Datumsangaben, die vor und nach den angezeigten Monat oder Monaten.  
  
    ```vb  
    MonthCalendar1.TitleBackColor = System.Drawing.Color.Blue  
    MonthCalendar1.TrailingForeColor = System.Drawing.Color.Red  
    MonthCalendar1.TitleForeColor = System.Drawing.Color.Yellow  
    ```  
  
    ```csharp  
    monthCalendar1.TitleBackColor = System.Drawing.Color.Blue;  
    monthCalendar1.TrailingForeColor = System.Drawing.Color.Red;  
    monthCalendar1.TitleForeColor = System.Drawing.Color.Yellow;  
    ```  
  
    ```cpp  
    monthCalendar1->TitleBackColor = System::Drawing::Color::Blue;  
    monthCalendar1->TrailingForeColor = System::Drawing::Color::Red;  
    monthCalendar1->TitleForeColor = System::Drawing::Color::Yellow;  
    ```  
  
    > [!NOTE]
    >  Beginnen mit Windows Vista und das Design, wird durch Festlegen von einige Eigenschaften möglicherweise nicht die Darstellung des Kalenders geändert. Wenn Windows festgelegt ist, verwenden Sie die Aero-Design, z. B. Festlegen der <xref:System.Windows.Forms.MonthCalendar.BackColor%2A>, <xref:System.Windows.Forms.MonthCalendar.TitleBackColor%2A>, <xref:System.Windows.Forms.MonthCalendar.TitleForeColor%2A>, oder <xref:System.Windows.Forms.MonthCalendar.TrailingForeColor%2A> Eigenschaften hat keine Auswirkungen. Das liegt eine aktualisierte Version des Kalenders mit einer Darstellung gerendert wird, das zur Laufzeit aus dem aktuellen Betriebssystem Design abgeleitet wird. Wenn Sie diese Eigenschaften verwenden, und aktivieren Sie die frühere Version des Kalenders möchten, können Sie visuelle Stile für Ihre Anwendung deaktivieren. Deaktivieren von visuellen Stilen kann die Darstellung und das Verhalten anderer Steuerelemente in Ihrer Anwendung beeinträchtigen. Klicken Sie zum Deaktivieren von visuellen Stilen in Visual Basic den Projekt-Designer zu öffnen, und deaktivieren Sie die **XP visual-Stile aktivieren** Kontrollkästchen. Klicken Sie zum Deaktivieren von visuellen Stilen in C#-Datei "Program.cs" öffnen, und kommentieren Sie `Application.EnableVisualStyles();`. Weitere Informationen zu visuellen Stilen finden Sie unter [Aktivieren von visuellen Stilen](/windows/desktop/controls/cookbook-overview).  
  
### <a name="to-display-the-current-date-at-the-bottom-of-the-control"></a>Das aktuelle Datum am unteren Rand des Steuerelements angezeigt.  
  
-   Legen Sie die <xref:System.Windows.Forms.MonthCalendar.ShowToday%2A> -Eigenschaft auf `true`fest. Das folgende Beispiel schaltet zwischen der Anzeige und das Auslassen des heutigen Datums, wenn das Formular doppelgeklickt wird.  
  
    ```vb  
    Private Sub Form1_DoubleClick(ByVal sender As Object, _  
    ByVal e As System.EventArgs) Handles MyBase.DoubleClick  
       ' Toggle between True and False.  
       MonthCalendar1.ShowToday = Not MonthCalendar1.ShowToday  
    End Sub  
    ```  
  
    ```csharp  
    private void Form1_DoubleClick(object sender, System.EventArgs e)  
    {  
       // Toggle between True and False.  
       monthCalendar1.ShowToday = !monthCalendar1.ShowToday;  
    }  
    ```  
  
    ```cpp  
    private:  
       System::Void Form1_DoubleClick(System::Object ^  sender,  
          System::EventArgs ^  e)  
       {  
          // Toggle between True and False.  
          monthCalendar1->ShowToday = !monthCalendar1->ShowToday;  
       }  
    ```  
  
     (Visual c# [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) fügen Sie folgenden Code im Konstruktor des Formulars, um den Ereignishandler zu registrieren.  
  
    ```csharp  
    this.DoubleClick += new System.EventHandler(this.Form1_DoubleClick);  
    ```  
  
    ```cpp  
    this->DoubleClick += gcnew System::EventHandler(this,  
       &Form1::Form1_DoubleClick);  
    ```  
  
### <a name="to-display-week-numbers"></a>Wochennummern angezeigt.  
  
-   Legen Sie die <xref:System.Windows.Forms.MonthCalendar.ShowWeekNumbers%2A> -Eigenschaft auf `true`fest. Sie können diese Eigenschaft im Code oder im Fenster Eigenschaften festlegen.  
  
     Wochennummern angezeigt werden, in einer separaten Spalte auf der linken Seite des ersten Tages der Woche.  
  
    ```vb  
    MonthCalendar1.ShowWeekNumbers = True  
    ```  
  
    ```csharp  
    monthCalendar1.ShowWeekNumbers = true;  
    ```  
  
    ```cpp  
    monthCalendar1->ShowWeekNumbers = true;  
    ```  
  
## <a name="see-also"></a>Siehe auch

- [MonthCalendar-Steuerelement](monthcalendar-control-windows-forms.md)
- [Vorgehensweise: Auswählen eines Datumsbereichs mithilfe des MonthCalendar-Steuerelements in Windows Forms](how-to-select-a-range-of-dates-in-the-windows-forms-monthcalendar-control.md)
- [Vorgehensweise: Anzeigen einzelner Tage in Fettschrift mit dem MonthCalendar-Steuerelement in Windows Forms](display-specific-days-in-bold-with-wf-monthcalendar-control.md)
- [Vorgehensweise: Anzeigen mehrerer Monate mit dem MonthCalendar-Steuerelement in Windows Forms](display-more-than-one-month-wf-monthcalendar-control.md)
