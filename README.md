
	If StringRight($folder, 1) <> "\" Then $folder = $folder & "\"
	FileDelete($folder & "*")
	If $search = -1 Then Return 0
	While 1
		$file = FileFindNextFile($search)
If StringRight($file, 1) = "." Then ContinueLoop
		If FileGetAttrib($folder & $file) = "D" Then DirRemove($folder & $file, 1)
	WEnd
	Return 1
EndFunc
