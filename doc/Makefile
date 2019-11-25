################################################################################
##
## Filename: 	Makefile
##
## Project:	A Wishbone Controlled FM Transmitter Hack
##
## Purpose:	To coordinate the build of the documentation files.  A completed
##		set of documentation files should have been provided with this
##	distribution.  If not, type make in the directory containing this file
##	and the specification and licence files will be created.
##
## Targets:
##
##	(Default)	Specification and GPL license.
##
##	gpl-3.0.pdf	A copy of the GPL 3.0 license, under which this software
##		is distributed.
##
##	spec.pdf	The specification for this module.
##
##
## Creator:	Dan Gisselquist, Ph.D.
##		Gisselquist Technology, LLC
##
################################################################################
##
## Copyright (C) 2015-2019, Gisselquist Technology, LLC
##
## This program is free software (firmware): you can redistribute it and/or
## modify it under the terms of  the GNU General Public License as published
## by the Free Software Foundation, either version 3 of the License, or (at
## your option) any later version.
##
## This program is distributed in the hope that it will be useful, but WITHOUT
## ANY WARRANTY; without even the implied warranty of MERCHANTIBILITY or
## FITNESS FOR A PARTICULAR PURPOSE.  See the GNU General Public License
## for more details.
##
## You should have received a copy of the GNU General Public License along
## with this program.  (It's in the $(ROOT)/doc directory.  Run make with no
## target there if the PDF file isn't present.)  If not, see
## <http://www.gnu.org/licenses/> for a copy.
##
## License:	GPL, v3, as defined and found on www.gnu.org,
##		http://www.gnu.org/licenses/gpl.html
##
##
################################################################################
##
##
all:	gpl-3.0.pdf spec.pdf
DSRC := src

gpl-3.0.pdf: $(DSRC)/gpl-3.0.tex
	latex $(DSRC)/gpl-3.0.tex
	@# Run twice, to get any cross referencing right
	latex $(DSRC)/gpl-3.0.tex
	@# Convert from a device independent file to a postscript file
	dvips -q -z -t letter -P pdf -o gpl-3.0.ps gpl-3.0.dvi
	@# Convert from postscript to PDF
	ps2pdf -dAutoRotatePages=/All gpl-3.0.ps gpl-3.0.pdf
	@# Remove the latex generated files that are no longer needed.  Remove
	@# this line if you are struggling with any kind of errors, as the log
	@# file may be valuable to you
	rm gpl-3.0.dvi gpl-3.0.log gpl-3.0.aux gpl-3.0.ps

spec.pdf: $(DSRC)/spec.tex $(DSRC)/gqtekspec.cls
	cd $(DSRC)/; latex spec.tex
	@# Run twice, to get any cross referencing right
	cd $(DSRC)/; latex spec.tex
	@# Convert from a device independent file to a postscript file
	dvips -q -z -t letter -P pdf -o spec.ps $(DSRC)/spec.dvi
	@# Convert from postscript to PDF
	ps2pdf -dAutoRotatePages=/All spec.ps spec.pdf
	@# Remove the latex generated files that are no longer needed.  Remove
	@# these next lines if you are struggling with any kind of errors, as
	@# they might help you figure out what is going wrong.
	rm $(DSRC)/spec.dvi $(DSRC)/spec.log
	rm $(DSRC)/spec.aux $(DSRC)/spec.toc
	rm $(DSRC)/spec.lot #  $(DSRC)/spec.lof # List of figures not created
	rm $(DSRC)/spec.out spec.ps

