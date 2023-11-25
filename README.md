# StoreManagment-project-VB.net
a VB.net project for manage store



 Imports System.Data.SqlClient
Imports System.Windows.Forms.VisualStyles.VisualStyleElement.StartPanel

Public Class Login

    'dragble bnane ke liye 
    Private Loc As Point

    Private Sub BunifuGradientPanel1_MouseDown(sender As Object, e As MouseEventArgs) Handles BunifuGradientPanel1.MouseDown
        If e.Button = Windows.Forms.MouseButtons.Left Then
            Loc = e.Location
        End If
    End Sub

    Private Sub BunifuGradientPanel1_MouseMove(sender As Object, e As MouseEventArgs) Handles BunifuGradientPanel1.MouseMove
        If e.Button = Windows.Forms.MouseButtons.Left Then
            Me.Location = New Point(Me.Location.X + (e.Location.X - Loc.X), Me.Location.Y + (e.Location.Y - Loc.Y))
        End If
    End Sub


    Private Sub BunifuImageButton2_Click(sender As Object, e As EventArgs)
        If Me.WindowState = FormWindowState.Normal Then
            Me.WindowState = FormWindowState.Maximized
        Else
            Me.WindowState = FormWindowState.Normal
        End If
    End Sub

    Private Sub BunifuImageButton2_Click_1(sender As Object, e As EventArgs) Handles BunifuImageButton2.Click
        Me.WindowState = FormWindowState.Minimized
    End Sub

    Private Sub BunifuImageButton4_Click(sender As Object, e As EventArgs) Handles BunifuImageButton4.Click
        Application.Exit()
    End Sub

    Private Sub BunifuThinButton22_Click(sender As Object, e As EventArgs) Handles BunifuThinButton22.Click
        Try
            If username.Text = "" Or password.Text = "" Then
                MsgBox("Enter The Username and Password")
                MsgBox("Contact Navneet Kashyap for ID Password")
            ElseIf username.Text = "Navneet" AndAlso password.Text = "Kashyap" Then
                Dim Obj = New item
                Obj.Show()
                Me.Hide()
            Else
                MsgBox("Wrong Username and Password")
                MsgBox("Contact Navneet Kashyap for ID Password")
                username.Text = ""
                password.Text = ""
            End If
        Catch ex As Exception
            MsgBox("Error: " & ex.Message)
        End Try
    End Sub


    Private Sub BunifuThinButton21_Click(sender As Object, e As EventArgs) Handles BunifuThinButton21.Click
        Try
            Dim Obj = New Order
            Obj.Show()
            Me.Hide()
        Catch ex As Exception
            MsgBox("Error: " & ex.Message)
        End Try
    End Sub

End Class
