PROJ_NAME = snakemini
SRC = minisnake.c src/snake_operation.c

TEST_SRC = src/snake_operation.c Test/test_operation.c Unity/unity.c
TEST_NAME = test_result

#To check if the snakeoperation.dows or linux and set the executable file extension and delete command accordingly
ifdef OS
   RM = del /q
   FixPath = $(subst /,\,$1)
   EXEC = exe
else
   ifeq ($(shell uname), Linux)
      RM = rm -rf
      FixPath = $1
	  EXEC = out
   endif
endif

build:
	gcc $(SRC) -o $(call FixPath,$(PROJ_NAME).$(EXEC)) -lm

run: build
	./$(call FixPath,$(PROJ_NAME).$(EXEC))
test: 
	gcc $(TEST_SRC) -o $(call FixPath,$(TEST_NAME).$(EXEC))  

clean:
	$(RM) $(call FixPath,$(PROJ_NAME).$(EXEC))
