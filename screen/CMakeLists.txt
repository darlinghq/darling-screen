project(screen)

set(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -nostdinc")

add_darling_executable(screen
	acls.c
	ansi.c
	attacher.c
	braille.c
	braille_tsi.c
	comm.c
	display.c
	encoding.c
	fileio.c
	help.c
	input.c
	kmapdef.c
	layer.c
	loadav.c
	logfile.c
	mark.c
	misc.c
	nethack.c
	process.c
	pty.c
	putenv.c
	resize.c
	screen.c
	search.c
	sched.c
	socket.c
	teln.c
	term.c
	termcap.c
	tty.c
	utmp.c
	window.c
)
target_link_libraries(screen system ncurses)

install(TARGETS screen DESTINATION libexec/darling/usr/bin)

install(FILES etc/screenrc DESTINATION libexec/darling/private/etc)
install(FILES doc/screen.1 DESTINATION libexec/darling/usr/share/man/man1)
install(DIRECTORY utf8encodings DESTINATION libexec/darling/usr/share)

